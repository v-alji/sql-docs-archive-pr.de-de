---
title: Ausführen des Systemmonitors | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- System Monitor [SQL Server], running
- Windows System Monitor [SQL Server], running
- remote procedure calls [SQL Server]
- starting Windows NT System Monitor
- RPC
ms.assetid: 05297984-bc8d-43df-829c-032387f7ea61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3dd0baf32402d69e36dc5120d0259b2f8d689897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723710"
---
# <a name="run-system-monitor"></a><span data-ttu-id="e00c8-102">Ausführen des Systemmonitors</span><span class="sxs-lookup"><span data-stu-id="e00c8-102">Run System Monitor</span></span>
  <span data-ttu-id="e00c8-103">Der Systemmonitor verwendet zum Sammeln von Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Informationen Remoteprozeduraufrufe (RPC).</span><span class="sxs-lookup"><span data-stu-id="e00c8-103">System Monitor uses remote procedure calls (RPCs) to collect information from Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e00c8-104">Jeder Benutzer, der über die entsprechenden Microsoft Windows-Berechtigungen zum Ausführen des Systemmonitors verfügt, kann dieses Tool für die Überwachung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="e00c8-104">Any user who has Microsoft Windows permissions to run System Monitor can use System Monitor to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e00c8-105">Bei der Verwendung des Systemmonitors können Sie keine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen, die unter Microsoft Windows 98 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e00c8-105">When using System Monitor or Performance Monitor, you cannot connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on Windows 98.</span></span>  
  
 <span data-ttu-id="e00c8-106">Wie bei allen Leistungsüberwachung ist auch bei der Verwendung des Systemmonitor zum Überwachen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]mit zusätzlichem Verarbeitungsaufwand zu rechnen.</span><span class="sxs-lookup"><span data-stu-id="e00c8-106">As with all performance monitoring tools, expect some performance overhead when you use System Monitor to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e00c8-107">Der tatsächliche Verarbeitungsaufwand in einer bestimmten Instanz hängt von der Hardwareplattform, der Anzahl der Leistungsindikatoren und dem ausgewählten Updateintervall ab.</span><span class="sxs-lookup"><span data-stu-id="e00c8-107">The actual overhead in any specific instance depends on the hardware platform, the number of counters, and the selected update interval.</span></span> <span data-ttu-id="e00c8-108">Die Integration des Systemmonitors mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ist jedoch so konzipiert, dass die Auswirkungen minimal sein sollten.</span><span class="sxs-lookup"><span data-stu-id="e00c8-108">However, the integration of System Monitor with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is designed to minimize any reduction in performance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e00c8-109">Wenn Sie im Snap-In des Systemmonitors [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Leistungsindikatoren zur Überwachung ausgewählt haben, werden die Leistungsindikatoren auch dann angezeigt, wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e00c8-109">If you have selected [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performance counters to monitor in the System Monitor snap-in, you will see the counters even if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not running.</span></span>  
  
 <span data-ttu-id="e00c8-110">Weitere Informationen zum Starten des Systemmonitors finden Sie unter [Starten des Systemmonitors &#40;Windows&#41;](../performance/start-system-monitor-windows.md).</span><span class="sxs-lookup"><span data-stu-id="e00c8-110">For information about starting System Monitor, see [Start System Monitor &#40;Windows&#41;](../performance/start-system-monitor-windows.md).</span></span>  
  
  
