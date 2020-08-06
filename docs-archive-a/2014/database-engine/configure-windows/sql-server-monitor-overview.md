---
title: SQL Server-Monitor (Übersicht) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlservermonitor.main.f1
helpviewer_keywords:
- SQL Server Monitor [SQL Server]
ms.assetid: 048ae16d-31c3-489a-9f1e-1400a3bacd39
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab90186ed493e616e672cfacf881fd61be166f88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608835"
---
# <a name="sql-server-monitor-overview"></a><span data-ttu-id="9149a-102">SQL Server-Monitor (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="9149a-102">SQL Server Monitor Overview</span></span>
  <span data-ttu-id="9149a-103">SQL Server-Monitor führt keine Überwachungsfunktionen aus, hostet jedoch Module, die diese Funktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="9149a-103">SQL Server Monitor does not perform monitoring functions, but it hosts modules that do.</span></span> <span data-ttu-id="9149a-104">Zu den SQL Server-Monitor-Modulen gehören der Replikationsmonitor und der Datenbankspiegelungs-Monitor.</span><span class="sxs-lookup"><span data-stu-id="9149a-104">The SQL Server Monitor modules include Replication Monitor and Database Mirroring Monitor.</span></span>  
  
 <span data-ttu-id="9149a-105">Wählen Sie das betreffende Modul im Menü **Wechseln zu** aus, um eines dieser Module zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9149a-105">To use one of these modules, select that module on the **Go** menu.</span></span> <span data-ttu-id="9149a-106">Das aktuell ausgewählte Modul ist im Besitz des Inhalts der Navigations- und Detailbereiche, der Benutzerinteraktionen in den Detailbereichen und der Abfragen für Inhalt und Status.</span><span class="sxs-lookup"><span data-stu-id="9149a-106">The currently selected module owns the content of the navigation and detail panes, user interaction in the detail panes, and the queries for content and status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9149a-107">Weitere Informationen zu diesen Monitoren finden Sie unter [Überwachen der Replikation](../../relational-databases/replication/monitoring-replication.md) und [Überwachen der Datenbankspiegelung &#40;SQL Server&#41;](../database-mirroring/database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9149a-107">For more information about these monitors, see [Monitoring Replication](../../relational-databases/replication/monitoring-replication.md) and [Monitoring Database Mirroring &#40;SQL Server&#41;](../database-mirroring/database-mirroring-sql-server.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="9149a-108">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9149a-108">Permissions</span></span>  
  
-   <span data-ttu-id="9149a-109">Replikationsmonitor</span><span class="sxs-lookup"><span data-stu-id="9149a-109">Replication Monitor</span></span>  
  
     <span data-ttu-id="9149a-110">Zum Überwachen der Replikation müssen Sie Mitglied der festen Serverrolle **sysadmin** auf dem Verteiler oder Mitglied der festen Datenbankrolle **replmonitor** in der Verteilungsdatenbank sein.</span><span class="sxs-lookup"><span data-stu-id="9149a-110">To monitor replication, you must be a member of the **sysadmin** fixed server role at the Distributor or a member of the **replmonitor** fixed database role in the distribution database.</span></span> <span data-ttu-id="9149a-111">Ein Systemadministrator kann jeden Benutzer zur **replmonitor** -Rolle hinzufügen. Anhand dieser Rolle kann ein Benutzer die Replikationsaktivität im Replikationsmonitor anzeigen. Er kann die Replikation jedoch nicht verwalten.</span><span class="sxs-lookup"><span data-stu-id="9149a-111">A system administrator can add any user to the **replmonitor** role, which allows that user to view replication activity in Replication Monitor; however, the user cannot administer replication.</span></span>  
  
-   <span data-ttu-id="9149a-112">Datenbankspiegelungs-Monitor</span><span class="sxs-lookup"><span data-stu-id="9149a-112">Database Mirroring Monitor</span></span>  
  
     <span data-ttu-id="9149a-113">Zum Überwachen der Datenbankspiegelung müssen Sie entweder Mitglied der festen Serverrolle **sysadmin** oder der festen Datenbankrolle **dbm_monitor** in der Serverinstanz sein.</span><span class="sxs-lookup"><span data-stu-id="9149a-113">To monitor database mirroring, you must be a member of either the **sysadmin** fixed server role or the **dbm_monitor** fixed database role on the server instance.</span></span> <span data-ttu-id="9149a-114">Wenn Sie Mitglied von **sysadmin** oder **dbm_monitor** auf nur einer der Partnerserverinstanzen sind, kann der Monitor nur mit diesem Partner eine Verbindung herstellen. Der Monitor kann keine Informationen von dem anderen Partner abrufen.</span><span class="sxs-lookup"><span data-stu-id="9149a-114">If you are a member of **sysadmin** or **dbm_monitor** on only one of the partner server instances, the monitor can connect only to that partner; the monitor cannot retrieve information from the other partner.</span></span> <span data-ttu-id="9149a-115">Weitere Informationen finden Sie unter [Database Mirroring Monitor Overview](../database-mirroring/database-mirroring-monitor-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9149a-115">For more information, see [Database Mirroring Monitor Overview](../database-mirroring/database-mirroring-monitor-overview.md).</span></span>  
  
## <a name="menu-options"></a><span data-ttu-id="9149a-116">Menüoptionen</span><span class="sxs-lookup"><span data-stu-id="9149a-116">Menu Options</span></span>  
 <span data-ttu-id="9149a-117">Der SQL Server-Monitor hat ein Menü mit Befehlen, die sich auf den SQL Server-Monitor beziehen.</span><span class="sxs-lookup"><span data-stu-id="9149a-117">SQL Server Monitor has a menu that contains commands that pertain to SQL Server Monitor.</span></span> <span data-ttu-id="9149a-118">Dieses Menü kann auch Befehle des ausgewählten Moduls enthalten.</span><span class="sxs-lookup"><span data-stu-id="9149a-118">This menu may also contain commands from the selected module.</span></span>  
  
 <span data-ttu-id="9149a-119">Die folgenden Menüoptionen beziehen sich auf den SQL Server-Monitor.</span><span class="sxs-lookup"><span data-stu-id="9149a-119">The following menu options pertain to SQL Server Monitor.</span></span>  
  
 <span data-ttu-id="9149a-120">**File**</span><span class="sxs-lookup"><span data-stu-id="9149a-120">**File**</span></span>  
 <span data-ttu-id="9149a-121">Das Menü enthält den Befehl **Beenden** .</span><span class="sxs-lookup"><span data-stu-id="9149a-121">This menu contains the **Exit** command.</span></span>  
  
 <span data-ttu-id="9149a-122">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="9149a-122">**Action**</span></span>  
 <span data-ttu-id="9149a-123">Enthält das Kontextmenü des Knotens, der in der Navigationsstruktur ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="9149a-123">Contains the context menu of the node selected in the navigation tree.</span></span>  
  
 <span data-ttu-id="9149a-124">**Go**</span><span class="sxs-lookup"><span data-stu-id="9149a-124">**Go**</span></span>  
 <span data-ttu-id="9149a-125">Enthält eine Liste mit Überwachungskomponenten:</span><span class="sxs-lookup"><span data-stu-id="9149a-125">Contains a list of monitoring components:</span></span>  
  
-   <span data-ttu-id="9149a-126">Datenbankspiegelung</span><span class="sxs-lookup"><span data-stu-id="9149a-126">Database Mirroring</span></span>  
  
-   <span data-ttu-id="9149a-127">Replikation</span><span class="sxs-lookup"><span data-stu-id="9149a-127">Replication</span></span>  
  
 <span data-ttu-id="9149a-128">**So verwenden Sie SQL Server Management Studio zum Überwachen der Datenbankspiegelung**</span><span class="sxs-lookup"><span data-stu-id="9149a-128">**To use SQL Server Management Studio to monitor database mirroring**</span></span>  
  
-   [<span data-ttu-id="9149a-129">Starten des Datenbankspiegelungs-Monitors &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9149a-129">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="9149a-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9149a-130">See Also</span></span>  
 [<span data-ttu-id="9149a-131">Überwachen der Datenbankspiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9149a-131">Monitoring Database Mirroring &#40;SQL Server&#41;</span></span>](../database-mirroring/database-mirroring-sql-server.md)  
  
  
