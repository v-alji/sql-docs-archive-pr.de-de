---
title: Überwachen der Datenträgerverwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- database monitoring [SQL Server], disk usage
- disks [SQL Server]
- monitoring performance [SQL Server], disk usage
- server performance [SQL Server], disk usage
- monitoring [SQL Server], disk activity
- excess paging [SQL Server]
- tuning databases [SQL Server], disk usage
- I/O [SQL Server], monitoring
- disks [SQL Server], monitoring activity
- isolating disk activity [SQL Server]
- database performance [SQL Server], disk usage
- monitoring server performance [SQL Server], disk usage
ms.assetid: 1525449c-ea7d-4222-b294-1ba1fe99c9ac
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 51479b024864322d34dc3b0208e29e93d7454184
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723725"
---
# <a name="monitor-disk-usage"></a><span data-ttu-id="fc933-102">Überwachen der Datenträgerverwendung</span><span class="sxs-lookup"><span data-stu-id="fc933-102">Monitor Disk Usage</span></span>
  <span data-ttu-id="fc933-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet Aufrufe für die Microsoft Windows-Betriebssystemeingabe/-ausgabe, um Lese- und Schreibvorgänge auf dem Datenträger auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fc933-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses Microsoft Windows operating system input/output (I/O) calls to perform read and write operations on your disk.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fc933-104">verwaltet wann und wie Datenträger-E/A ausgeführt wird, aber das Windows-Betriebssystem führt die zugrunde liegenden E/A-Vorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="fc933-104">manages when and how disk I/O is performed, but the Windows operating system performs the underlying I/O operations.</span></span> <span data-ttu-id="fc933-105">Das E/A-Teilsystem umfasst Systembus, Datenträgercontrollerkarten, Datenträger, Bandlaufwerke, CD-ROM-Laufwerk und zahlreiche andere E/A-Geräte.</span><span class="sxs-lookup"><span data-stu-id="fc933-105">The I/O subsystem includes the system bus, disk controller cards, disks, tape drives, CD-ROM drive, and many other I/O devices.</span></span> <span data-ttu-id="fc933-106">Datenträger-E/A ist häufig die Ursache von Engpässen in einem System.</span><span class="sxs-lookup"><span data-stu-id="fc933-106">Disk I/O is frequently the cause of bottlenecks in a system.</span></span>  
  
 <span data-ttu-id="fc933-107">Die Überwachung der Datenträgeraktivitäten ist auf zwei Bereiche konzentriert:</span><span class="sxs-lookup"><span data-stu-id="fc933-107">Monitoring disk activity involves two areas of focus:</span></span>  
  
-   <span data-ttu-id="fc933-108">Überwachen der Datenträger-E/A und Erkennen von zu häufigem Auslagern</span><span class="sxs-lookup"><span data-stu-id="fc933-108">Monitoring Disk I/O and Detecting Excess Paging</span></span>  
  
-   <span data-ttu-id="fc933-109">Isolieren der Datenträgeraktivitäten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc933-109">Isolating Disk Activity That [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Creates</span></span>  
  
 <span data-ttu-id="fc933-110">Weitere Informationen finden Sie unter Überwachen der Datenträger [Verwendung](https://social.technet.microsoft.com/wiki/contents/articles/monitoring-disk-usage.aspx) .</span><span class="sxs-lookup"><span data-stu-id="fc933-110">For more information see, [Monitoring Disk Usage](https://social.technet.microsoft.com/wiki/contents/articles/monitoring-disk-usage.aspx)</span></span>  
  
  
