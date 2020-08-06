---
title: SQL Server-Agent-Eigenschaften (Seite Erweitert)|Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.advanced.f1
ms.assetid: a4d798ee-4c18-40d4-b6af-63d17503738c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8ec0d9d7fbd51f9350bf692588f90c292e54f4e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621313"
---
# <a name="sql-server-agent-properties-advanced-page"></a><span data-ttu-id="4bdb5-102">SQL Server-Agent-Eigenschaften (Seite Erweitert)</span><span class="sxs-lookup"><span data-stu-id="4bdb5-102">SQL Server Agent Properties (Advanced Page)</span></span>
  <span data-ttu-id="4bdb5-103">Verwenden Sie diese Seite, um erweiterte Eigenschaften des- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Dienstanbieter anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4bdb5-103">Use this page to view and modify advanced properties of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4bdb5-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4bdb5-104">Options</span></span>  
 <span data-ttu-id="4bdb5-105">**SQL Server-Ereignisweiterleitung**</span><span class="sxs-lookup"><span data-stu-id="4bdb5-105">**SQL Server event forwarding**</span></span>  
 <span data-ttu-id="4bdb5-106">Durch die Optionen in dieser Kategorie wird die Ereignisweiterleitung aktiviert und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4bdb5-106">The options in this category activate and configure event forwarding.</span></span>  
  
 <span data-ttu-id="4bdb5-107">**Ereignisse an anderen Server weiterleiten**</span><span class="sxs-lookup"><span data-stu-id="4bdb5-107">**Forward events to a different server**</span></span>  
 <span data-ttu-id="4bdb5-108">Leitet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Ereignisse an einen anderen Server weiter.</span><span class="sxs-lookup"><span data-stu-id="4bdb5-108">Forwards [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events to a different server.</span></span>  
  
 <span data-ttu-id="4bdb5-109">**Server**</span><span class="sxs-lookup"><span data-stu-id="4bdb5-109">**Server**</span></span>  
 <span data-ttu-id="4bdb5-110">Wählen Sie den Namen des Servers aus, an den Ereignisse weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4bdb5-110">Select the name of the server to forward events to.</span></span>  
  
 <span data-ttu-id="4bdb5-111">**Ereignisse ohne Behandlung**</span><span class="sxs-lookup"><span data-stu-id="4bdb5-111">**Unhandled events**</span></span>  
 <span data-ttu-id="4bdb5-112">Leitet nur Ereignisse ohne Behandlung an den angegebenen Server weiter.</span><span class="sxs-lookup"><span data-stu-id="4bdb5-112">Forwards only unhandled events to the specified server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4bdb5-113">Agent leitet nur Ereignisse weiter, auf die keine Warnung reagiert.</span><span class="sxs-lookup"><span data-stu-id="4bdb5-113">Agent forwards only events that no alert responds to.</span></span>  
  
 <span data-ttu-id="4bdb5-114">**Alle Ereignisse**</span><span class="sxs-lookup"><span data-stu-id="4bdb5-114">**All events**</span></span>  
 <span data-ttu-id="4bdb5-115">Leitet alle Ereignisse weiter.</span><span class="sxs-lookup"><span data-stu-id="4bdb5-115">Forwards all events.</span></span> <span data-ttu-id="4bdb5-116">Wenn eine Warnung in der lokalen Instanz auf das Ereignis reagiert, leitet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] das Ereignis weiter und verarbeitet auch die Warnung.</span><span class="sxs-lookup"><span data-stu-id="4bdb5-116">When an alert in the local instance responds to the event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent will both forward the event and process the alert.</span></span>  
  
 <span data-ttu-id="4bdb5-117">**Bei diesem Schweregrad des Ereignisses oder darüber**</span><span class="sxs-lookup"><span data-stu-id="4bdb5-117">**If event has severity at or above**</span></span>  
 <span data-ttu-id="4bdb5-118">Leitet nur Ereignisse weiter, deren Schweregrad der angegebenen Ebene entspricht oder darüber liegt.</span><span class="sxs-lookup"><span data-stu-id="4bdb5-118">Forwards only events with a severity level at or above the level specified.</span></span>  
  
 <span data-ttu-id="4bdb5-119">**Bedingung für 'CPU im Leerlauf'**</span><span class="sxs-lookup"><span data-stu-id="4bdb5-119">**Idle CPU Condition**</span></span>  
 <span data-ttu-id="4bdb5-120">Durch die Optionen in dieser Kategorie werden die Bedingungen definiert, unter denen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Aufträge ausführt, für die CPU-Leerlaufzeitpläne festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="4bdb5-120">The options in this category define the conditions under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs jobs scheduled to run on the Idle CPU schedule.</span></span>  
  
 <span data-ttu-id="4bdb5-121">**Bedingung für 'CPU im Leerlauf' definieren**</span><span class="sxs-lookup"><span data-stu-id="4bdb5-121">**Define idle CPU condition**</span></span>  
 <span data-ttu-id="4bdb5-122">Definiert die Bedingungen, unter denen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent die CPU als im Leerlauf befindlich betrachtet.</span><span class="sxs-lookup"><span data-stu-id="4bdb5-122">Defines the conditions under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent considers the CPU to be idle.</span></span>  
  
 <span data-ttu-id="4bdb5-123">**bei durchschnittlicher CPU-Nutzung unter**</span><span class="sxs-lookup"><span data-stu-id="4bdb5-123">**Average CPU usage falls below**</span></span>  
 <span data-ttu-id="4bdb5-124">Prozentualer Wert der CPU-Nutzung, unter dem die CPU als im Leerlauf befindlich betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="4bdb5-124">Percentage of CPU usage below which the CPU is considered to be idle.</span></span>  
  
 <span data-ttu-id="4bdb5-125">**und Verbleiben unterhalb dieser Stufe für**</span><span class="sxs-lookup"><span data-stu-id="4bdb5-125">**And remains below this level for**</span></span>  
 <span data-ttu-id="4bdb5-126">Die Zeitspanne, für die die durchschnittliche CPU-Nutzung unterhalb des angegebenen Wertes liegen muss, bevor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Aufträge dem CPU-Leerlaufzeitplan entsprechend ausführt.</span><span class="sxs-lookup"><span data-stu-id="4bdb5-126">Amount of time that the average CPU must below the level specified before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs jobs on the Idle CPU schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bdb5-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4bdb5-127">See Also</span></span>  
 <span data-ttu-id="4bdb5-128">[Erstellen und Anfügen von Zeitplänen an Aufträge](create-and-attach-schedules-to-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="4bdb5-128">[Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md) </span></span>  
 [<span data-ttu-id="4bdb5-129">Verwalten von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="4bdb5-129">Manage Events</span></span>](manage-events.md)  
  
  
