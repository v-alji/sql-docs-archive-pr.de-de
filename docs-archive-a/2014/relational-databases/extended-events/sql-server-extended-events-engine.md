---
title: Engine für erweiterte Ereignisse von SQL Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], engine
ms.assetid: d74642a5-42b9-4a15-aa3d-f98bfe695050
author: rothja
ms.author: jroth
ms.openlocfilehash: ef11ac8e2cfaf39d2bca90f1d5d52439989ee327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608660"
---
# <a name="sql-server-extended-events-engine"></a><span data-ttu-id="b7c37-102">Engine für erweiterte Ereignisse von SQL Server</span><span class="sxs-lookup"><span data-stu-id="b7c37-102">SQL Server Extended Events Engine</span></span>
  <span data-ttu-id="b7c37-103">Die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events-Engine ist eine Sammlung von Diensten und Objekten, die:</span><span class="sxs-lookup"><span data-stu-id="b7c37-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events engine is a collection of services and objects that:</span></span>  
  
-   <span data-ttu-id="b7c37-104">die Definition von Ereignissen ermöglichen,</span><span class="sxs-lookup"><span data-stu-id="b7c37-104">Enable the definition of events.</span></span>  
  
-   <span data-ttu-id="b7c37-105">die Verarbeitung von Ereignisdaten ermöglichen,</span><span class="sxs-lookup"><span data-stu-id="b7c37-105">Enable processing event data.</span></span>  
  
-   <span data-ttu-id="b7c37-106">Dienste und Objekte für erweiterte Ereignisse im System verwalten und</span><span class="sxs-lookup"><span data-stu-id="b7c37-106">Manage Extended Events services and objects in the system.</span></span>  
  
-   <span data-ttu-id="b7c37-107">eine Liste von Sitzungen für erweiterte Ereignisse führen und den Zugriff auf diese Liste verwalten.</span><span class="sxs-lookup"><span data-stu-id="b7c37-107">Maintain a list of Extended Events sessions and manage access to that list.</span></span>  
  
 <span data-ttu-id="b7c37-108">Die Engine für erweiterte Ereignisse selbst stellt keine Ereignisse oder beim Auslösen eines Ereignisses erforderlichen Aktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="b7c37-108">The Extended Events engine itself does not provide any events or actions to take when an event fires.</span></span> <span data-ttu-id="b7c37-109">Die Prozesse, die die Engine für erweiterte Ereignisse verwenden, definieren die Interaktion mit der Engine.</span><span class="sxs-lookup"><span data-stu-id="b7c37-109">The processes that use the Extended Events engine define interaction with the engine.</span></span> <span data-ttu-id="b7c37-110">Diese Prozesse fügen Ereignispunkte hinzu und stellen die bei Auslösung eines Ereignisses erforderlichen Aktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="b7c37-110">These processes add event points and supply the actions to take in response to event firing.</span></span>  
  
 <span data-ttu-id="b7c37-111">Die folgende Abbildung zeigt eine vereinfachte Ansicht einer Sitzung für erweiterte Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="b7c37-111">The following illustration shows a simplified view of an Extended Events session.</span></span> <span data-ttu-id="b7c37-112">Weitere Informationen finden Sie unter [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="b7c37-112">For more information, see [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span></span>  
  
 <span data-ttu-id="b7c37-113">![Detaillierte Architektur von erweiterten Ereignissen](../../database-engine/media/xearchitecturedetailed.gif "Detaillierte Architektur von erweiterten Ereignissen")</span><span class="sxs-lookup"><span data-stu-id="b7c37-113">![Detailed extended events architecture](../../database-engine/media/xearchitecturedetailed.gif "Detailed extended events architecture")</span></span>  
  
 <span data-ttu-id="b7c37-114">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b7c37-114">Note the following:</span></span>  
  
-   <span data-ttu-id="b7c37-115">Jeder Windows-Prozess kann über ein oder mehrere Module (**Win32-Prozess**, **Win32-Modul**) verfügen.</span><span class="sxs-lookup"><span data-stu-id="b7c37-115">Each Windows process can have one or more modules (**Win32 process**, **Win32 module**).</span></span> <span data-ttu-id="b7c37-116">Diese werden auch als *Binärdateien* oder *ausführbare Module*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b7c37-116">These are also known as *binaries* or *executable modules*.</span></span>  
  
-   <span data-ttu-id="b7c37-117">Jedes Windows-Prozessmodul kann mindestens ein Paket für erweiterte Ereignisse (**Paket**) enthalten, das wiederum mindestens ein Objekt für erweiterte Ereignisse (**Typ**, **Ziel**, **Aktion**, **Zuordnung**, **Prädikat**und **Ereignis**) enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="b7c37-117">Each of the Windows process modules can contain one or more Extended Events packages (**Package**), which contain one or more Extended Events objects (**Type**, **Target**, **Action**, **Map**, **Predicate**, and **Event**).</span></span>  
  
-   <span data-ttu-id="b7c37-118">Ein Hostprozess kann nur eine Instanz der Engine für erweiterte Ereignisse (**Engine für erweiterte Ereignisse**) aufweisen. Dieses führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="b7c37-118">Inside a host process there can only be one instance of the Extended Events engine (**Extended event engine**), which:</span></span>  
  
    -   <span data-ttu-id="b7c37-119">Es verwaltet einige Aspekte der Sitzung (z. B. das Aufzählen von Sitzungen).</span><span class="sxs-lookup"><span data-stu-id="b7c37-119">Manages some aspects of the session (for example, enumerating sessions).</span></span>  
  
    -   <span data-ttu-id="b7c37-120">Es übernimmt die Verteilung (**Verteiler**).</span><span class="sxs-lookup"><span data-stu-id="b7c37-120">Handles dispatching (**Dispatcher**).</span></span> <span data-ttu-id="b7c37-121">Dies ist mit einem Threadpool vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="b7c37-121">This is similar to a thread pool.</span></span>  
  
    -   <span data-ttu-id="b7c37-122">Es verarbeitet Speicherpuffer (**Puffer**) für Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="b7c37-122">Handles memory buffers (**Buffer**) for events.</span></span> <span data-ttu-id="b7c37-123">Wenn Puffer aufgefüllt sind, werden sie an Ziele verteilt.</span><span class="sxs-lookup"><span data-stu-id="b7c37-123">When buffers are filled, the buffers are dispatched to targets.</span></span>  
  
-   <span data-ttu-id="b7c37-124">Wenn eine Sitzung erstellt wurde und optional Ereignisse an die Sitzung (**Sitzungskontext**) gebunden wurden:</span><span class="sxs-lookup"><span data-stu-id="b7c37-124">After a session is created and events are optionally bound to the session (**Session context**):</span></span>  
  
    -   <span data-ttu-id="b7c37-125">Es können auch Instanzen von Zielen (**Zielinstanz**) erstellt und der Sitzung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b7c37-125">Instances of targets (**Target instance**) may be also be created and added to the session.</span></span>  
  
    -   <span data-ttu-id="b7c37-126">Wenn Puffer aufgefüllt sind, werden diese an Ziele verteilt.</span><span class="sxs-lookup"><span data-stu-id="b7c37-126">When buffers are filled, those buffers are dispatched to targets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7c37-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7c37-127">See Also</span></span>  
 [<span data-ttu-id="b7c37-128">Erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="b7c37-128">Extended Events</span></span>](extended-events.md)  
  
  
