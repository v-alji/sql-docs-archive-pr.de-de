---
title: Ausführen von Aufträgen zur Replikationswartung (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server replication]
ms.assetid: 0dc485a0-5a50-41eb-a29d-f2b2fb920174
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9dc27c65e96a9f956ffa6d3edf9c72ed52f721a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721401"
---
# <a name="run-replication-maintenance-jobs-sql-server-management-studio"></a><span data-ttu-id="d1138-102">Ausführen von Aufträgen zur Replikationswartung (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d1138-102">Run Replication Maintenance Jobs (SQL Server Management Studio)</span></span>
  <span data-ttu-id="d1138-103">Bei der Replikation werden folgende Wartungsaufträge verwendet:</span><span class="sxs-lookup"><span data-stu-id="d1138-103">Replication uses the following maintenance jobs:</span></span>  
  
-   <span data-ttu-id="d1138-104">**Abonnements mit Datenüberprüfungsfehlern neu initialisieren**</span><span class="sxs-lookup"><span data-stu-id="d1138-104">**Reinitialize subscriptions having data validation failures**</span></span>
-   <span data-ttu-id="d1138-105">**Agentverlaufscleanup: Verteilung**</span><span class="sxs-lookup"><span data-stu-id="d1138-105">**Agent history clean up: distribution**</span></span>
-   <span data-ttu-id="d1138-106">**Aktualisierung für die Replikationsüberwachung für Verteilung.**</span><span class="sxs-lookup"><span data-stu-id="d1138-106">**Replication monitoring refresher for distribution.**</span></span>
-   <span data-ttu-id="d1138-107">**Überprüfung des Replikations-Agents**</span><span class="sxs-lookup"><span data-stu-id="d1138-107">**Replication agents checkup**</span></span>
-   <span data-ttu-id="d1138-108">**Verteilungscleanup: Verteilung**</span><span class="sxs-lookup"><span data-stu-id="d1138-108">**Distribution clean up: distribution**</span></span>
-   <span data-ttu-id="d1138-109">**Cleanup abgelaufener Abonnements**</span><span class="sxs-lookup"><span data-stu-id="d1138-109">**Expired subscription clean up**</span></span>  
  
 <span data-ttu-id="d1138-110">Diese Aufträge können über den Ordner **Aufträge** in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] sowie über die Registerkarte **Agents** im Replikationsmonitor gestartet und beendet werden.</span><span class="sxs-lookup"><span data-stu-id="d1138-110">Start and stop these jobs from the **Jobs** folder in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from the **Agents** tab in Replication Monitor.</span></span> <span data-ttu-id="d1138-111">Informationen zum Starten des Replikationsmonitors finden Sie unter [Starten des Replikationsmonitors](../monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="d1138-111">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span> <span data-ttu-id="d1138-112">Die Eigenschaften der einzelnen Aufträge können im Dialogfeld **Auftragseigenschaften - \<Job>** angezeigt und überprüft werden. Der Zugriff hierauf ist über denselben Ordner/dieselbe Registerkarte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d1138-112">View and modify properties for each job in the **Job Properties - \<Job>** dialog box, which is available from the same folder and tab.</span></span>  
  
### <a name="to-start-or-stop-a-replication-maintenance-job-in-management-studio"></a><span data-ttu-id="d1138-113">So starten Sie einen Auftrag zur Replikationswartung in Management Studio</span><span class="sxs-lookup"><span data-stu-id="d1138-113">To start or stop a replication maintenance job in Management Studio</span></span>  
  
1.  <span data-ttu-id="d1138-114">Stellen Sie in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Verteiler her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="d1138-114">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="d1138-115">Erweitern Sie den Ordner **SQL Server-Agent** und anschließend den Ordner **Aufträge** .</span><span class="sxs-lookup"><span data-stu-id="d1138-115">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="d1138-116">Klicken Sie mit der rechten Maustaste auf einen Auftrag, und klicken Sie dann auf **Auftrag starten** oder **Auftrag beenden**.</span><span class="sxs-lookup"><span data-stu-id="d1138-116">Right-click a job, and then click **Start Job** or **Stop Job**.</span></span>  
  
### <a name="to-start-or-stop-a-replication-maintenance-job-in-replication-monitor"></a><span data-ttu-id="d1138-117">So starten Sie einen Auftrag zur Replikationswartung im Replikationsmonitor</span><span class="sxs-lookup"><span data-stu-id="d1138-117">To start or stop a replication maintenance job in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="d1138-118">Erweitern Sie im Replikationsmonitor eine Verlegergruppe, und wählen Sie dann einen Verleger aus.</span><span class="sxs-lookup"><span data-stu-id="d1138-118">Expand a Publisher group in Replication Monitor, and then select a Publisher.</span></span>  
  
2.  <span data-ttu-id="d1138-119">Klicken Sie auf die Registerkarte **Agents** .</span><span class="sxs-lookup"><span data-stu-id="d1138-119">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="d1138-120">Klicken Sie mit der rechten Maustaste auf einen Auftrag, und klicken Sie dann auf **Auftrag starten** oder **Auftrag beenden**.</span><span class="sxs-lookup"><span data-stu-id="d1138-120">Right-click a job in the grid, and then click **Start Job** or **Stop Job**.</span></span>  
  
### <a name="to-view-and-modify-properties-for-a-replication-maintenance-job-in-management-studio"></a><span data-ttu-id="d1138-121">So zeigen Sie Eigenschaften für einen Auftrag zur Replikationswartung in Management Studio an oder ändern sie</span><span class="sxs-lookup"><span data-stu-id="d1138-121">To view and modify properties for a replication maintenance job in Management Studio</span></span>  
  
1.  <span data-ttu-id="d1138-122">Stellen Sie in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Verteiler her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="d1138-122">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="d1138-123">Erweitern Sie den Ordner **SQL Server-Agent** und anschließend den Ordner **Aufträge** .</span><span class="sxs-lookup"><span data-stu-id="d1138-123">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="d1138-124">Klicken Sie mit der rechten Maustaste auf einen Auftrag, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d1138-124">Right-click a job, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="d1138-125">Ändern Sie im Dialogfeld **Auftragseigenschaften - \<Job>** bei Bedarf Eigenschaften, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1138-125">In the **Job Properties - \<Job>** dialog box, modify any properties if necessary, and then click **OK**.</span></span>  
  
### <a name="to-view-and-modify-properties-for-a-replication-maintenance-job-in-replication-monitor"></a><span data-ttu-id="d1138-126">So zeigen Sie Eigenschaften für einen Auftrag zur Replikationswartung im Replikationsmonitor an oder ändern sie</span><span class="sxs-lookup"><span data-stu-id="d1138-126">To view and modify properties for a replication maintenance job in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="d1138-127">Erweitern Sie im Replikationsmonitor eine Verlegergruppe, und wählen Sie dann einen Verleger aus.</span><span class="sxs-lookup"><span data-stu-id="d1138-127">Expand a Publisher group in Replication Monitor, and then select a Publisher.</span></span>  
  
2.  <span data-ttu-id="d1138-128">Klicken Sie auf die Registerkarte **Agents** .</span><span class="sxs-lookup"><span data-stu-id="d1138-128">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="d1138-129">Klicken Sie mit der rechten Maustaste auf einen Auftrag im Raster, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d1138-129">Right-click a job in the grid, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="d1138-130">Ändern Sie im Dialogfeld **Auftragseigenschaften - \<Job>** bei Bedarf Eigenschaften, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1138-130">In the **Job Properties - \<Job>** dialog box, modify any properties if necessary, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1138-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d1138-131">See Also</span></span>  
 <span data-ttu-id="d1138-132">[Starten und Beenden eines Replikations-Agents &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d1138-132">[Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="d1138-133">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](../monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="d1138-133">[View Information and Perform Tasks using Replication Monitor](../monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="d1138-134">Replikations-Agent-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="d1138-134">Replication Agent Administration</span></span>](../agents/replication-agent-administration.md)  
  
  
