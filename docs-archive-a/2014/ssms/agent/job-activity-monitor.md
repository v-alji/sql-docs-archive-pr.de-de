---
title: Auftragsaktivitätsmonitor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.ACTIVITYMON.F1
- sql12.ag.jobactivitymonitor.alljobs.f1
ms.assetid: 11f2182c-5f71-46f8-8d2b-74f0fc48f2d6
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6f89d5448f0885c85229c2808ee6f85bf6fa071
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699219"
---
# <a name="job-activity-monitor"></a><span data-ttu-id="70f27-102">Auftragsaktivitätsmonitor</span><span class="sxs-lookup"><span data-stu-id="70f27-102">Job Activity Monitor</span></span>
  <span data-ttu-id="70f27-103">Mithilfe dieser Seite können Sie die aktuelle Aktivität von Aufträgen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents anzeigen.</span><span class="sxs-lookup"><span data-stu-id="70f27-103">Use this page to view the current activity of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span> <span data-ttu-id="70f27-104">Klicken Sie auf **Filter** , um die Anzahl der angezeigten Aufträge zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="70f27-104">Click **Filter** to limit the jobs displayed.</span></span> <span data-ttu-id="70f27-105">Das Raster **Agentauftragsaktivität** ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="70f27-105">The **Agent Job Activity** grid is read-only.</span></span> <span data-ttu-id="70f27-106">Klicken Sie auf die Spaltenheader, um das Raster zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="70f27-106">Click on the column headers to sort the grid.</span></span> <span data-ttu-id="70f27-107">Sie können einen Auftrag ändern, indem Sie auf den betreffenden Auftrag doppelklicken und das Dialogfeld **Auftragseigenschaften** öffnen.</span><span class="sxs-lookup"><span data-stu-id="70f27-107">To modify a job, double-click the job to open the **Job Properties** dialog box.</span></span> <span data-ttu-id="70f27-108">Klicken Sie mit der rechten Maustaste auf einen Auftrag im Raster, um die Ausführung aller Auftragsschritte zu starten, einen speziellen Auftragsschritt zu starten, den Auftrag zu aktivieren oder zu deaktivieren, den Auftrag zu aktualisieren, den Auftrag zu löschen, den Verlauf des Auftrags anzuzeigen oder die Auftragseigenschaften anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="70f27-108">Right-click a job in the grid to start it running all job steps, start at a particular job step, disable or enable the job, refresh the job, delete the job, view the history of the job, or view the properties of the job.</span></span> <span data-ttu-id="70f27-109">Klicken Sie auf **Aktualisieren** , um das Raster mit den aktuellen Informationen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="70f27-109">Click **Refresh** to update the grid with current information.</span></span>  
  
## <a name="options"></a><span data-ttu-id="70f27-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="70f27-110">Options</span></span>  
 <span data-ttu-id="70f27-111">**Name**</span><span class="sxs-lookup"><span data-stu-id="70f27-111">**Name**</span></span>  
 <span data-ttu-id="70f27-112">Der Name des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="70f27-112">Name of the job.</span></span>  
  
 <span data-ttu-id="70f27-113">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="70f27-113">**Enabled**</span></span>  
 <span data-ttu-id="70f27-114">Zeigt an, ob der Auftrag aktiviert (**Ja**) oder nicht aktiviert (**Nein**) ist.</span><span class="sxs-lookup"><span data-stu-id="70f27-114">Whether the job is enabled (**yes**) or not enabled (**no**).</span></span>  
  
 <span data-ttu-id="70f27-115">**Status** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="70f27-115">**Status** <sup>1</sup></span></span>  
 <span data-ttu-id="70f27-116">Aktueller Status des Auftrags</span><span class="sxs-lookup"><span data-stu-id="70f27-116">Current status of the job.</span></span>  
  
 <span data-ttu-id="70f27-117">**Ergebnis der letzten Ausführung**</span><span class="sxs-lookup"><span data-stu-id="70f27-117">**Last Run Outcome**</span></span>  
 <span data-ttu-id="70f27-118">Auftragsstatus bei der letzten Ausführung</span><span class="sxs-lookup"><span data-stu-id="70f27-118">Job status when last run.</span></span>  
  
 <span data-ttu-id="70f27-119">**Zuletzt ausgeführt**</span><span class="sxs-lookup"><span data-stu-id="70f27-119">**Last Run**</span></span>  
 <span data-ttu-id="70f27-120">Datum und Uhrzeit, an dem bzw. zu der der Auftrag zuletzt ausgeführt wurde (ausgehend vom lokalen Datum und der lokalen Uhrzeit des Servers).</span><span class="sxs-lookup"><span data-stu-id="70f27-120">Date and time job was last run using the local date and time of the server.</span></span>  
  
 <span data-ttu-id="70f27-121">**Nächste ausführen** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="70f27-121">**Next Run** <sup>1</sup></span></span>  
 <span data-ttu-id="70f27-122">Datum und Uhrzeit des Zeitpunkts, an dem die nächste Ausführung des Auftrags geplant ist (ausgehend vom lokalen Datum und der lokalen Uhrzeit des Servers).</span><span class="sxs-lookup"><span data-stu-id="70f27-122">Date and time the job is next scheduled to run using the local date and time of the server.</span></span>  
  
 <span data-ttu-id="70f27-123">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="70f27-123">**Category**</span></span>  
 <span data-ttu-id="70f27-124">Die dem Auftrag zugewiesene Auftragskategorie.</span><span class="sxs-lookup"><span data-stu-id="70f27-124">The job category assigned to the job.</span></span>  
  
 <span data-ttu-id="70f27-125">**Ausführbaren**</span><span class="sxs-lookup"><span data-stu-id="70f27-125">**Runnable**</span></span>  
 <span data-ttu-id="70f27-126">**Ja** , wenn der Auftrag ausgeführt werden kann; **Nein** , wenn der Auftrag nicht ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="70f27-126">**Yes** if the job can be run; **No** if the job cannot be run.</span></span> <span data-ttu-id="70f27-127">Ein Auftrag kann nicht ausgeführt werden, wenn er keine Schritte oder keinen Zielserver aufweist.</span><span class="sxs-lookup"><span data-stu-id="70f27-127">A job is not runnable if it has no steps or if it has no target server.</span></span>  
  
 <span data-ttu-id="70f27-128">**Geplant**</span><span class="sxs-lookup"><span data-stu-id="70f27-128">**Scheduled**</span></span>  
 <span data-ttu-id="70f27-129">**Ja** , wenn der Auftrag einem Auftragszeitplan zugewiesen ist; **Nein** , wenn für den Auftrag kein Zeitplan vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="70f27-129">**Yes** if the job is assigned to a job schedule; **No** if the job has no schedule.</span></span>  
  
 <span data-ttu-id="70f27-130"><sup>1</sup> Nur Mitglieder der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] festen Server Rolle sysadmin und der Server Administrator Gruppe können Werte in dieser Spalte sehen.</span><span class="sxs-lookup"><span data-stu-id="70f27-130"><sup>1</sup>Only members of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sysadmin fixed server role and the server administrators group can see values in this column.</span></span> <span data-ttu-id="70f27-131">Mitglieder der SQLAgentOperatorRole-Rolle können keine Werte in dieser Spalte sehen.</span><span class="sxs-lookup"><span data-stu-id="70f27-131">Members of the SQLAgentOperatorRole role cannot see values in this column.</span></span>  
  
#### <a name="to-open-the-job-activity-monitor"></a><span data-ttu-id="70f27-132">So öffnen Sie den Auftragsaktivitätsmonitor</span><span class="sxs-lookup"><span data-stu-id="70f27-132">To open the Job Activity Monitor</span></span>  
  
-   <span data-ttu-id="70f27-133">Erweitern Sie in **Objekt-Explorer**den verwendeten Server und anschließend **SQL Server-Agent**. Klicken Sie mit der rechten Maustaste auf **Auftragsaktivitätsmonitor**, und klicken Sie dann auf **Auftragsaktivitäten anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="70f27-133">In **Object Explorer**, expand your server, expand **SQL Server Agent**, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f27-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70f27-134">See Also</span></span>  
 [<span data-ttu-id="70f27-135">Überwachen der Auftragsaktivität</span><span class="sxs-lookup"><span data-stu-id="70f27-135">Monitor Job Activity</span></span>](monitor-job-activity.md)  
  
  
