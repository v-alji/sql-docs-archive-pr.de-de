---
title: SQL Server, Latches-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Latches object
- SQLServer:Latches
ms.assetid: 2393ea1c-2bf3-41c3-9f37-b9761144eeca
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6f49ac00114065e971c0893f9217ab883eb2d7f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609834"
---
# <a name="sql-server-latches-object"></a><span data-ttu-id="ff35f-102">SQL Server, Latches-Objekt</span><span class="sxs-lookup"><span data-stu-id="ff35f-102">SQL Server, Latches Object</span></span>
  <span data-ttu-id="ff35f-103">Das **SQLServer:Latches** -Objekt in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enthält Leistungsindikatoren zur Überwachung interner [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ressourcensperren, die als Latches bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="ff35f-103">The **SQLServer:Latches** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor internal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource locks called latches.</span></span> <span data-ttu-id="ff35f-104">Das Überwachen der Latches für die Ermittlung der Benutzeraktivität und der Ressourcennutzung kann Ihnen dabei helfen, Leistungsengpässe zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="ff35f-104">Monitoring the latches to determine user activity and resource usage can help you to identify performance bottlenecks.</span></span>  
  
 <span data-ttu-id="ff35f-105">In dieser Tabelle werden die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Leistungsindikatoren **Latches** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ff35f-105">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Latches** counters.</span></span>  
  
|<span data-ttu-id="ff35f-106">Batches-Leistungsindikatoren von SQL Server</span><span class="sxs-lookup"><span data-stu-id="ff35f-106">SQL Server Latches counters</span></span>|<span data-ttu-id="ff35f-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ff35f-107">Description</span></span>|  
|---------------------------------|-----------------|  
|<span data-ttu-id="ff35f-108">**Durchschnittliche Wartezeit für Latch (in Millisekunden)**</span><span class="sxs-lookup"><span data-stu-id="ff35f-108">**Average Latch Wait Time (ms)**</span></span>|<span data-ttu-id="ff35f-109">Durchschnittliche Latchwartezeit (in Millisekunden) für wartende Latchanforderungen.</span><span class="sxs-lookup"><span data-stu-id="ff35f-109">Average latch wait time (in milliseconds) for latch requests that had to wait.</span></span>|  
|<span data-ttu-id="ff35f-110">**Latchwartezeit/Sekunde**</span><span class="sxs-lookup"><span data-stu-id="ff35f-110">**Latch Waits/sec**</span></span>|<span data-ttu-id="ff35f-111">Anzahl der Latchanforderungen, für die Batches nicht sofort erteilt werden konnten.</span><span class="sxs-lookup"><span data-stu-id="ff35f-111">Number of latch requests that could not be granted immediately.</span></span>|  
|<span data-ttu-id="ff35f-112">**Anzahl der SuperLatches-Objekte**</span><span class="sxs-lookup"><span data-stu-id="ff35f-112">**Number of SuperLatches**</span></span>|<span data-ttu-id="ff35f-113">Anzahl der Batches, die zurzeit SuperLatches-Objekte sind.</span><span class="sxs-lookup"><span data-stu-id="ff35f-113">Number of latches that are currently SuperLatches.</span></span>|  
|<span data-ttu-id="ff35f-114">**SuperLatches-Heraufstufungen/Sekunde**</span><span class="sxs-lookup"><span data-stu-id="ff35f-114">**SuperLatch Demotions/sec**</span></span>|<span data-ttu-id="ff35f-115">Anzahl der SuperLatches-Objekte, die in der letzten Sekunde zu normalen Batches herabgestuft wurden.</span><span class="sxs-lookup"><span data-stu-id="ff35f-115">Number of SuperLatches that have been demoted to regular latches in the last second.</span></span>|  
|<span data-ttu-id="ff35f-116">**SuperLatches-Höherstufungen/Sekunde**</span><span class="sxs-lookup"><span data-stu-id="ff35f-116">**SuperLatch Promotions/sec**</span></span>|<span data-ttu-id="ff35f-117">Anzahl der Batches, die in der letzten Sekunde zu SuperLatches-Objekten heraufgestuft wurden.</span><span class="sxs-lookup"><span data-stu-id="ff35f-117">Number of latches that have been promoted to SuperLatches in the last second.</span></span>|  
|<span data-ttu-id="ff35f-118">**Gesamtwartezeit für Latch (in Millisekunden)**</span><span class="sxs-lookup"><span data-stu-id="ff35f-118">**Total Latch Wait Time (ms)**</span></span>|<span data-ttu-id="ff35f-119">Gesamtwartezeit (in Millisekunden) für Latchanforderungen, die in der vergangenen Sekunde warten mussten.</span><span class="sxs-lookup"><span data-stu-id="ff35f-119">Total latch wait time (in milliseconds) for latch requests in the last second.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ff35f-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff35f-120">See Also</span></span>  
 [<span data-ttu-id="ff35f-121">Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;</span><span class="sxs-lookup"><span data-stu-id="ff35f-121">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
