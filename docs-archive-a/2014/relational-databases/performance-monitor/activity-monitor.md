---
title: Aktivitätsmonitor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Activity Monitor [SQL Server]
ms.assetid: 1e6c430d-3a2a-468e-a3d5-ef5459c36c15
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 71fd0d1172b4fcd5739a3af1a60246cc7dce3b93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723734"
---
# <a name="activity-monitor"></a><span data-ttu-id="f80e1-102">Aktivitätsmonitor</span><span class="sxs-lookup"><span data-stu-id="f80e1-102">Activity Monitor</span></span>
  <span data-ttu-id="f80e1-103">Im Aktivitätsmonitor werden Informationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Prozessen angezeigt sowie Informationen dazu, welche Auswirkungen diese Prozesse auf die aktuelle Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]haben.</span><span class="sxs-lookup"><span data-stu-id="f80e1-103">Activity Monitor displays information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes and how these processes affect the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="benefits-of-activity-monitor"></a><span data-ttu-id="f80e1-104">Vorteile des Aktivitätsmonitors</span><span class="sxs-lookup"><span data-stu-id="f80e1-104">Benefits of Activity Monitor</span></span>  
 <span data-ttu-id="f80e1-105">Der Aktivitäts Monitor ist ein Dokument Fenster im Register Format mit den folgenden erweiterbaren und reduzierbaren Bereichen: **Übersicht**, **aktive Benutzer Tasks**, **Ressourcen warte**Vorgänge, **Datendatei-e/** a und **aktuelle teure Abfragen**.</span><span class="sxs-lookup"><span data-stu-id="f80e1-105">Activity Monitor is a tabbed document window that has the following expandable and collapsible panes: **Overview**, **Active User Tasks**, **Resource Waits**, **Data File I/O**, and **Recent Expensive Queries**.</span></span> <span data-ttu-id="f80e1-106">Wenn ein Bereich erweitert wird, fragt der Aktivitätsmonitor die Instanz nach Informationen ab.</span><span class="sxs-lookup"><span data-stu-id="f80e1-106">When any pane is expanded, Activity Monitor queries the instance for information.</span></span> <span data-ttu-id="f80e1-107">Wenn ein Bereich reduziert wird, werden sämtliche Abfrageaktivitäten für diesen Bereich angehalten.</span><span class="sxs-lookup"><span data-stu-id="f80e1-107">When a pane is collapsed, all querying activity stops for that pane.</span></span> <span data-ttu-id="f80e1-108">Sie können auch einen oder mehrere Bereiche gleichzeitig erweitern, um unterschiedliche Aktivitätstypen für die Instanz anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f80e1-108">You can also expand one or more panes at the same time to view different kinds of activity on the instance.</span></span>  
  
 <span data-ttu-id="f80e1-109">Für die Spalten, die in den Bereichen **aktive Benutzer Tasks**, **Ressourcen warte**Vorgänge, **Datendatei-e/** a und **aktuelle teure Abfragen** enthalten sind, können Sie die Anzeige auf folgende Weise anpassen:</span><span class="sxs-lookup"><span data-stu-id="f80e1-109">For the columns that are included in the **Active User Tasks**, **Resource Waits**, **Data File I/O**, and **Recent Expensive Queries** panes, you can customize the display in the following ways:</span></span>  
  
1.  <span data-ttu-id="f80e1-110">Um die Reihenfolge der Spalten zu ändern, klicken Sie auf die Spaltenüberschrift, und ziehen Sie diese an eine andere Stelle des Menübands.</span><span class="sxs-lookup"><span data-stu-id="f80e1-110">To rearrange the order of the columns, click the column heading and drag it to another location in the heading ribbon.</span></span>  
  
2.  <span data-ttu-id="f80e1-111">Um eine Spalte zu sortieren, klicken Sie auf den Spaltennamen.</span><span class="sxs-lookup"><span data-stu-id="f80e1-111">To sort a column, click the column name.</span></span>  
  
3.  <span data-ttu-id="f80e1-112">Um eine oder mehrere Spalten zu filtern, klicken Sie in der Spaltenüberschrift auf den Dropdownpfeil, und wählen Sie anschließend einen Wert aus.</span><span class="sxs-lookup"><span data-stu-id="f80e1-112">To filter on one or more columns, click the drop-down arrow in the column heading, and then select a value.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f80e1-113">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f80e1-113">Related Tasks</span></span>  
 <span data-ttu-id="f80e1-114">Verwenden Sie für die ersten Schritte mit dem Aktivitätsmonitor die folgenden Tasks:</span><span class="sxs-lookup"><span data-stu-id="f80e1-114">Use the following tasks to get started with Activity Monitor:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f80e1-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f80e1-115">**Description**</span></span>|<span data-ttu-id="f80e1-116">**Thema**</span><span class="sxs-lookup"><span data-stu-id="f80e1-116">**Topic**</span></span>|  
|<span data-ttu-id="f80e1-117">Beschreibt das Öffnen des Aktivitätsmonitors und das Festlegen des Aktualisierungsintervalls für den Aktivitätsmonitor.</span><span class="sxs-lookup"><span data-stu-id="f80e1-117">Describes how to open Activity Monitor and how to set the Activity Monitor refresh interval.</span></span>|[<span data-ttu-id="f80e1-118">Öffnen des Aktivitätsmonitors &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f80e1-118">Open Activity Monitor &#40;SQL Server Management Studio&#41;</span></span>](../performance-monitor/open-activity-monitor-sql-server-management-studio.md)|  
|<span data-ttu-id="f80e1-119">Stellt Links zu Themen zum Überwachen der Serverleistung und -aktivität bereit.</span><span class="sxs-lookup"><span data-stu-id="f80e1-119">Links to topics for server performance and activity monitoring.</span></span>|[<span data-ttu-id="f80e1-120">Überwachen der Serverleistung und -aktivität</span><span class="sxs-lookup"><span data-stu-id="f80e1-120">Server Performance and Activity Monitoring</span></span>](../performance/server-performance-and-activity-monitoring.md)|  
  
  
