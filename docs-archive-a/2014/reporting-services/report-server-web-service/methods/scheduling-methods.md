---
title: Zeitplanmethoden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- schedules [Reporting Services], methods
- reports [Reporting Services], scheduling
- shared schedules [Reporting Services], methods
- methods [Reporting Services], scheduling
ms.assetid: 68ae13f9-d91e-4572-a82a-8fa42001569e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 735da4f22d523fd40dd031f55e203fa9a4204f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609630"
---
# <a name="scheduling-methods"></a><span data-ttu-id="ed7b1-102">Zeitplanmethoden</span><span class="sxs-lookup"><span data-stu-id="ed7b1-102">Scheduling Methods</span></span>
  <span data-ttu-id="ed7b1-103">Sie können diese Methoden verwenden, um freigegebene Zeitpläne für die Berichtsausführung und -übermittlung zu erstellen und zu verwalten und die vom Berichtsserver verwendeten Aktualisierungspläne zwischenzuspeichern.</span><span class="sxs-lookup"><span data-stu-id="ed7b1-103">You can use these methods to create and manage shared schedules for report execution and delivery, and to cache refresh plans utilized by the report server.</span></span>  
  
|<span data-ttu-id="ed7b1-104">Methode</span><span class="sxs-lookup"><span data-stu-id="ed7b1-104">Method</span></span>|<span data-ttu-id="ed7b1-105">Aktion</span><span class="sxs-lookup"><span data-stu-id="ed7b1-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateCacheRefreshPlan%2A>|<span data-ttu-id="ed7b1-106">Erstellt einen Cacheaktualisierungsplan für ein Element.</span><span class="sxs-lookup"><span data-stu-id="ed7b1-106">Creates a cache refresh plan for an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.CreateSchedule%2A>|<span data-ttu-id="ed7b1-107">Erstellt einen neuen freigegebenen Zeitplan.</span><span class="sxs-lookup"><span data-stu-id="ed7b1-107">Creates a new shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteCacheRefreshPlan%2A>|<span data-ttu-id="ed7b1-108">Löscht einen Cacheaktualisierungsplan.</span><span class="sxs-lookup"><span data-stu-id="ed7b1-108">Deletes a cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteSchedule%2A>|<span data-ttu-id="ed7b1-109">Löscht einen freigegebenen Zeitplan auf Grundlage einer bestimmten Zeitplan-ID.</span><span class="sxs-lookup"><span data-stu-id="ed7b1-109">Deletes a shared schedule based on a specific schedule ID.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetCacheRefreshPlanProperties%2A>|<span data-ttu-id="ed7b1-110">Gibt die Eigenschaften des angegebenen Cacheaktualisierungsplans zurück.</span><span class="sxs-lookup"><span data-stu-id="ed7b1-110">Returns the properties of the specified cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetScheduleProperties%2A>|<span data-ttu-id="ed7b1-111">Gibt die Werte der Eigenschaften eines freigegebenen Zeitplans zurück.</span><span class="sxs-lookup"><span data-stu-id="ed7b1-111">Returns the values of properties of a shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListCacheRefreshPlans%2A>|<span data-ttu-id="ed7b1-112">Gibt eine Liste der einem Katalogelement zugeordneten Cacheaktualisierungspläne zurück.</span><span class="sxs-lookup"><span data-stu-id="ed7b1-112">Returns a list of the cache refresh plans associated with a catalog item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListScheduledItems%2A>|<span data-ttu-id="ed7b1-113">Gibt eine Liste von Elementen zurück, die zu einem freigegebenen Zeitplan gehören.</span><span class="sxs-lookup"><span data-stu-id="ed7b1-113">Returns a list of items that are associated with a shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListSchedules%2A>|<span data-ttu-id="ed7b1-114">Gibt eine Liste aller freigegebenen Zeitpläne auf dem Berichtsserver oder auf der SharePoint-Website zurück.</span><span class="sxs-lookup"><span data-stu-id="ed7b1-114">Returns a list of all shared schedules at the report server or the SharePoint site.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListScheduleStates%2A>|<span data-ttu-id="ed7b1-115">Gibt eine Liste unterstützter Zeitplanzustände zurück.</span><span class="sxs-lookup"><span data-stu-id="ed7b1-115">Returns a list of supported schedule states.</span></span>|  
|<xref:ReportService2010.ReportingService2010.PauseSchedule%2A>|<span data-ttu-id="ed7b1-116">Hält die Ausführung eines bestimmten Zeitplans an.</span><span class="sxs-lookup"><span data-stu-id="ed7b1-116">Pauses the execution of a given schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ResumeSchedule%2A>|<span data-ttu-id="ed7b1-117">Setzt die Ausführung eines freigegebenen Zeitplans fort, der angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="ed7b1-117">Resumes a shared schedule that has been paused.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetCacheRefreshPlanProperties%2A>|<span data-ttu-id="ed7b1-118">Legt die Eigenschaften eines Cacheaktualisierungsplans fest.</span><span class="sxs-lookup"><span data-stu-id="ed7b1-118">Sets the properties of a cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetScheduleProperties%2A>|<span data-ttu-id="ed7b1-119">Legt den Wert der Eigenschaften eines freigegebenen Zeitplans fest.</span><span class="sxs-lookup"><span data-stu-id="ed7b1-119">Sets the value of properties of a shared schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed7b1-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed7b1-120">See Also</span></span>  
 <span data-ttu-id="ed7b1-121">[Erstellen von Anwendungen mit dem Webdienst und .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="ed7b1-121">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="ed7b1-122">[Berichtsserver-Webdienst](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="ed7b1-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="ed7b1-123">[Webdienstmethoden für Berichtsserver](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="ed7b1-123">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="ed7b1-124">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="ed7b1-124">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
