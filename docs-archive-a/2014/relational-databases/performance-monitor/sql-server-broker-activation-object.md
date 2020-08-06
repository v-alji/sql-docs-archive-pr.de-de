---
title: SQL Server, Broker-Aktivierung-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Broker Activation
- Broker Activation object
ms.assetid: cd9b6880-c924-42c7-b333-09c303317c0b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4048c2baecaeb4bde7a1e215a15e8c51a60a01bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699519"
---
# <a name="sql-server-broker-activation-object"></a><span data-ttu-id="6191b-102">SQL Server, Broker-Aktivierung-Objekt</span><span class="sxs-lookup"><span data-stu-id="6191b-102">SQL Server, Broker Activation Object</span></span>
  <span data-ttu-id="6191b-103">Das Leistungsobjekt **SQLServer:Broker-Aktivierung** enthält Leistungsindikatoren, die Informationen über gespeicherte Aktivierungsprozeduren übermitteln.</span><span class="sxs-lookup"><span data-stu-id="6191b-103">The **SQLServer:BrokerActivation** performance object contains performance counters that report information on stored procedure activation.</span></span> <span data-ttu-id="6191b-104">In der nachfolgenden Tabelle sind die in diesem Objekt enthaltenen Indikatoren aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="6191b-104">The table below lists the counters that this object contains.</span></span>  
  
|<span data-ttu-id="6191b-105">SQL Server, Broker-Aktivierungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="6191b-105">SQL Server Broker Activation counters</span></span>|<span data-ttu-id="6191b-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6191b-106">Description</span></span>|  
|-------------------------------------------|-----------------|  
|<span data-ttu-id="6191b-107">**Aufruf von gespeicherten Prozeduren/Sekunde**</span><span class="sxs-lookup"><span data-stu-id="6191b-107">**Stored Procedures Invoked/sec**</span></span>|<span data-ttu-id="6191b-108">Dieser Indikator übermittelt die Gesamtzahl der gespeicherten Aktivierungsprozeduren, die pro Sekunde von allen Warteschlangenüberwachungen der Instanz aufgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="6191b-108">This counter reports the total number of activation stored procedures invoked by all queue monitors in the instance per second.</span></span>|  
|<span data-ttu-id="6191b-109">**Taskgrenze erreicht**</span><span class="sxs-lookup"><span data-stu-id="6191b-109">**Task Limit Reached**</span></span>|<span data-ttu-id="6191b-110">Dieser Indikator übermittelt, wie oft eine Warteschlangenüberwachung insgesamt einen neuen Task gestartet hätte, wenn nicht bereits die maximal für die Warteschlange zulässige Anzahl Tasks ausgeführt würde.</span><span class="sxs-lookup"><span data-stu-id="6191b-110">This counter reports the total number of times that a queue monitor would have started a new task, but did not because the maximum number of tasks for the queue is already running.</span></span>|  
|<span data-ttu-id="6191b-111">**Erreichte Taskgrenze/Sekunde**</span><span class="sxs-lookup"><span data-stu-id="6191b-111">**Task Limit Reached/sec**</span></span>|<span data-ttu-id="6191b-112">Dieser Indikator übermittelt, wie oft pro Sekunde eine Warteschlangenüberwachung einen neuen Task gestartet hätte, wenn nicht bereits die maximal für die Warteschlange zulässige Anzahl Tasks ausgeführt würde.</span><span class="sxs-lookup"><span data-stu-id="6191b-112">This counter reports the number of times per second that a queue monitor would have started a new task, but did not because the maximum number of tasks for the queue is already running.</span></span>|  
|<span data-ttu-id="6191b-113">**Abgebrochene Tasks/Sekunde**</span><span class="sxs-lookup"><span data-stu-id="6191b-113">**Tasks Aborted/sec**</span></span>|<span data-ttu-id="6191b-114">Dieser Indikator übermittelt die Anzahl der gespeicherten Aktivierungsprozeduraufgaben, die mit einem Fehler beendet oder wegen eines Fehlers beim Empfangen von Nachrichten über eine Warteschlangenüberwachung abgebrochen wurden.</span><span class="sxs-lookup"><span data-stu-id="6191b-114">This counter reports the number of activation stored procedure tasks that end with an error, or are aborted by a queue monitor for failing to receive messages.</span></span>|  
|<span data-ttu-id="6191b-115">**Ausgeführte Tasks**</span><span class="sxs-lookup"><span data-stu-id="6191b-115">**Tasks Running**</span></span>|<span data-ttu-id="6191b-116">Dieser Indikator übermittelt die Anzahl der gespeicherten Aktivierungsprozeduren, die zurzeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6191b-116">This counter reports the number of activation stored procedures that are currently running.</span></span>|  
|<span data-ttu-id="6191b-117">**Gestartete Tasks/Sekunde**</span><span class="sxs-lookup"><span data-stu-id="6191b-117">**Tasks Started/sec**</span></span>|<span data-ttu-id="6191b-118">Dieser Indikator übermittelt die Anzahl der gespeicherten Aktivierungsprozeduren, die von allen Warteschlangenüberwachungen der Instanz pro Sekunde gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="6191b-118">This counter reports the number of activation stored procedures started per second by all queue monitors in the instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6191b-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6191b-119">See Also</span></span>  
 <span data-ttu-id="6191b-120">[sys.dm_broker_activated_tasks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-activated-tasks-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6191b-120">[sys.dm_broker_activated_tasks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-activated-tasks-transact-sql) </span></span>  
 <span data-ttu-id="6191b-121">[sys.dm_broker_queue_monitors &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-queue-monitors-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6191b-121">[sys.dm_broker_queue_monitors &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-queue-monitors-transact-sql) </span></span>  
 [<span data-ttu-id="6191b-122">Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;</span><span class="sxs-lookup"><span data-stu-id="6191b-122">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
