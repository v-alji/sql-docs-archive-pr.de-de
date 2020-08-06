---
title: SQL Server, Speicherknoten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 55b28ba9-b6d5-4ea9-8103-db8a72f42982
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d5bbc3f581ea9ececeb7d55a614ef27c3c72de7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622041"
---
# <a name="sql-server-memory-node"></a><span data-ttu-id="16c33-102">SQL Server, Speicherknoten</span><span class="sxs-lookup"><span data-stu-id="16c33-102">SQL Server, Memory Node</span></span>
  <span data-ttu-id="16c33-103">Das **Speicherknoten** -Objekt in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stellt Leistungsindikatoren bereit, mit denen Sie die Speicherauslastung des Servers für NUMA-Knoten überwachen können.</span><span class="sxs-lookup"><span data-stu-id="16c33-103">The **Memory Node** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor server memory usage on NUMA nodes.</span></span>  
  
## <a name="memory-node-counters"></a><span data-ttu-id="16c33-104">Leistungsindikatoren für Speicherknoten</span><span class="sxs-lookup"><span data-stu-id="16c33-104">Memory Node Counters</span></span>  
 <span data-ttu-id="16c33-105">In dieser Tabelle sind die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Speicherknoten** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="16c33-105">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Memory Node** counters.</span></span>  
  
|<span data-ttu-id="16c33-106">Speicher-Manager-Leistungsindikatoren von SQL Server</span><span class="sxs-lookup"><span data-stu-id="16c33-106">SQL Server Memory Manager counters</span></span>|<span data-ttu-id="16c33-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="16c33-107">Description</span></span>|  
|----------------------------------------|-----------------|  
|<span data-ttu-id="16c33-108">**Datenbankknotenspeicher (KB)**</span><span class="sxs-lookup"><span data-stu-id="16c33-108">**Database Node Memory (KB)**</span></span>|<span data-ttu-id="16c33-109">Gibt den Arbeitsspeicher an, die der Server derzeit in diesem Knoten für Datenbankseiten verwendet.</span><span class="sxs-lookup"><span data-stu-id="16c33-109">Specifies the amount of memory the server is currently using on this node for database pages.</span></span>|  
|<span data-ttu-id="16c33-110">**Freier Knotenspeicher (KB)**</span><span class="sxs-lookup"><span data-stu-id="16c33-110">**Free Node Memory (KB)**</span></span>|<span data-ttu-id="16c33-111">Gibt den Arbeitsspeicher an, den der Server nicht in diesem Knoten verwendet.</span><span class="sxs-lookup"><span data-stu-id="16c33-111">Specifies the amount of memory the server is not using on this node.</span></span>|  
|<span data-ttu-id="16c33-112">**Fremder Knotenspeicher (KB)**</span><span class="sxs-lookup"><span data-stu-id="16c33-112">**Foreign Node Memory (KB)**</span></span>|<span data-ttu-id="16c33-113">Gibt die Menge des Arbeitsspeichers in diesem Knoten an, der kein Teil des lokalen NUMA-Arbeitsspeichers ist.</span><span class="sxs-lookup"><span data-stu-id="16c33-113">Specifies the amount of non NUMA-local memory on this node.</span></span>|  
|<span data-ttu-id="16c33-114">**Gestohlener Knotenspeicher (KB)**</span><span class="sxs-lookup"><span data-stu-id="16c33-114">**Stolen Memory Node (KB)**</span></span>|<span data-ttu-id="16c33-115">Gibt den Arbeitsspeicher an, die der Server derzeit in diesem Knoten für andere Zwecke als Datenbankseiten verwendet.</span><span class="sxs-lookup"><span data-stu-id="16c33-115">Specifies the amount of memory the server is using on this node for purposes other than database pages.</span></span>|  
|<span data-ttu-id="16c33-116">**Zielknotenspeicher**</span><span class="sxs-lookup"><span data-stu-id="16c33-116">**Target Node Memory**</span></span>|<span data-ttu-id="16c33-117">Gibt den idealen Arbeitsspeicher für diesen Knoten an.</span><span class="sxs-lookup"><span data-stu-id="16c33-117">Specifies the ideal amount of memory for this node.</span></span>|  
|<span data-ttu-id="16c33-118">**Gesamtknotenspeicher**</span><span class="sxs-lookup"><span data-stu-id="16c33-118">**Total Node Memory**</span></span>|<span data-ttu-id="16c33-119">Gibt die Gesamtmenge des Arbeitsspeichers an, für die der Server einen Commit in diesem Knoten ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="16c33-119">Indicates the total amount of memory the server has committed on this node.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16c33-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="16c33-120">See Also</span></span>  
 <span data-ttu-id="16c33-121">[Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;](monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="16c33-121">[Monitor Resource Usage &#40;System Monitor&#41;](monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="16c33-122">[SQL Server, Puffer-Manager-Objekt](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="16c33-122">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="16c33-123">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="16c33-123">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql)  
  
  
