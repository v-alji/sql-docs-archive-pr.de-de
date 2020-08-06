---
title: SQL Server-Agent, Alerts-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Alerts object
- SQLAgent:Alerts
ms.assetid: e5e37f74-ee88-46d0-ad8f-71fd1b1fa64a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9aa6fa871730af8cf129b3ea6b0aa4f1853d7e4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615350"
---
# <a name="sql-server-agent-alerts-object"></a><span data-ttu-id="ef03a-102">SQL Server-Agent, Warnungen-Objekt</span><span class="sxs-lookup"><span data-stu-id="ef03a-102">SQL Server Agent, Alerts Object</span></span>
  <span data-ttu-id="ef03a-103">Das Leistungsobjekt **Warnungen** des SQL Server-Agents enthält Leistungsindikatoren mit Informationen über SQL Server-Agent-Warnungen.</span><span class="sxs-lookup"><span data-stu-id="ef03a-103">The SQL Server Agent **Alerts** performance object contains performance counters that report information about SQL Server Agent alerts.</span></span> <span data-ttu-id="ef03a-104">In der nachfolgenden Tabelle sind die in diesem Objekt enthaltenen Indikatoren aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="ef03a-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="ef03a-105">Die folgende Tabelle enthält die Leistungsindikatoren **SQLAgent:Warnungen** .</span><span class="sxs-lookup"><span data-stu-id="ef03a-105">The table below contains the **SQLAgent:Alerts** counters.</span></span>  
  
|<span data-ttu-id="ef03a-106">Name</span><span class="sxs-lookup"><span data-stu-id="ef03a-106">Name</span></span>|<span data-ttu-id="ef03a-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ef03a-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="ef03a-108">**Aktivierte Warnungen**</span><span class="sxs-lookup"><span data-stu-id="ef03a-108">**Activated alerts**</span></span>|<span data-ttu-id="ef03a-109">Dieser Leistungsindikator berichtet die Gesamtanzahl der Warnungen, die der SQL Server-Agent seit dem letzten Neustart aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ef03a-109">This counter reports the total number of alerts that SQL Server Agent has activated since the last time that SQL Server Agent restarted.</span></span>|  
|<span data-ttu-id="ef03a-110">**Aktivierte Warnungen/Minute**</span><span class="sxs-lookup"><span data-stu-id="ef03a-110">**Alerts activated/minute**</span></span>|<span data-ttu-id="ef03a-111">Dieser Leistungsindikator berichtet die Anzahl der Warnungen, die der SQL Server-Agent innerhalb der letzten Minute aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ef03a-111">This counter reports the number of alerts that SQL Server Agent activated within the last minute.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="ef03a-112">Um dieses SQL Server-Agent-Objekt verwenden zu können, muss der Benutzer ein Mitglied der festen Serverrolle **sysadmin** sein.</span><span class="sxs-lookup"><span data-stu-id="ef03a-112">To use this SQL Server Agent object, users must be a member of the **sysadmin** fixed server role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef03a-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef03a-113">See Also</span></span>  
 <span data-ttu-id="ef03a-114">[Warnungen](../../ssms/agent/alerts.md) </span><span class="sxs-lookup"><span data-stu-id="ef03a-114">[Alerts](../../ssms/agent/alerts.md) </span></span>  
 <span data-ttu-id="ef03a-115">[Verwenden von Leistungsobjekten](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="ef03a-115">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="ef03a-116">Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;</span><span class="sxs-lookup"><span data-stu-id="ef03a-116">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
