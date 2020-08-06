---
title: SQL Server, Sicherungsmedium-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Backup Device
- Backup Device object
ms.assetid: 52e7febf-d5e0-4674-945b-aacc40a9ad6e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e3126310ad31dcc153fc79508dbfaccf86f5da78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616502"
---
# <a name="sql-server-backup-device-object"></a><span data-ttu-id="16c09-102">SQL Server, Sicherungsmedium-Objekt</span><span class="sxs-lookup"><span data-stu-id="16c09-102">SQL Server, Backup Device Object</span></span>
  <span data-ttu-id="16c09-103">Das **Sicherungsmedium** -Objekt stellt Leistungsindikatoren bereit, die mit denen für Sicherungs- und Wiederherstellungsvorgänge verwendeten Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherungsmedien überwacht werden können.</span><span class="sxs-lookup"><span data-stu-id="16c09-103">The **Backup Device** object provides counters to monitor Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup devices used for backup and restore operations.</span></span> <span data-ttu-id="16c09-104">Überwachen Sie Sicherungsmedien, wenn Sie den Durchsatz oder den Fortschritt und die Leistung der Sicherungs- und Wiederherstellungsvorgänge auf jedem Medium einzeln bestimmen möchten.</span><span class="sxs-lookup"><span data-stu-id="16c09-104">Monitor backup devices when you want to determine the throughput or the progress and performance of your backup and restore operations on a per device basis.</span></span> <span data-ttu-id="16c09-105">Wenn Sie den Durchsatz des gesamten Sicherungs- oder Wiederherstellungsvorgangs der Datenbank überwachen möchten, sollten Sie den Leistungsindikator **Sicherungs-/Wiederherstellungsdurchsatz/Sekunde** des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **-Datenbankobjekts** verwenden.</span><span class="sxs-lookup"><span data-stu-id="16c09-105">To monitor the throughput of the entire database backup or restore operation, use the **Backup/Restore Throughput/sec** counter of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Databases** object.</span></span> <span data-ttu-id="16c09-106">Weitere Informationen finden Sie unter [SQL Server, Databases Object](sql-server-databases-object.md).</span><span class="sxs-lookup"><span data-stu-id="16c09-106">For more information, see [SQL Server, Databases Object](sql-server-databases-object.md).</span></span>  
  
 <span data-ttu-id="16c09-107">In dieser Tabelle wird der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Leistungsindikator **Sicherungsmedium** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="16c09-107">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Backup Device** counter.</span></span>  
  
|<span data-ttu-id="16c09-108">Sicherungsmedium-Leistungsindikatoren von SQL Server</span><span class="sxs-lookup"><span data-stu-id="16c09-108">SQL Server Backup Device counters</span></span>|<span data-ttu-id="16c09-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="16c09-109">Description</span></span>|  
|---------------------------------------|-----------------|  
|<span data-ttu-id="16c09-110">**Mediumsdurchsatz Bytes/Sekunde**</span><span class="sxs-lookup"><span data-stu-id="16c09-110">**Device Throughput Bytes/sec**</span></span>|<span data-ttu-id="16c09-111">Durchsatz von Lese-/Schreibvorgängen für ein Sicherungsmedium.</span><span class="sxs-lookup"><span data-stu-id="16c09-111">Throughput of read and write operations (in bytes per second) for a backup device used when backing up or restoring databases.</span></span> <span data-ttu-id="16c09-112">Dieser Leistungsindikator ist nur vorhanden, während der Sicherungs- oder Wiederherstellungsvorgang ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="16c09-112">This counter exists only while the backup or restore operation is executing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16c09-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="16c09-113">See Also</span></span>  
 <span data-ttu-id="16c09-114">[Sicherungsmedien &#40;SQL Server&#41;](../backup-restore/backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="16c09-114">[Backup Devices &#40;SQL Server&#41;](../backup-restore/backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="16c09-115">Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;</span><span class="sxs-lookup"><span data-stu-id="16c09-115">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
