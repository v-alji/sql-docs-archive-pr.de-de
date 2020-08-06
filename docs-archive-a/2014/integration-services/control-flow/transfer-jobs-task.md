---
title: Aufträge übertragen (Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferjobstask.f1
helpviewer_keywords:
- Transfer Jobs task [Integration Services]
ms.assetid: 1bf33885-9c5b-47e4-a549-f5920b66a1de
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d692934d5f7c8c1449b123ee8b9caf1d8bb34744
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607920"
---
# <a name="transfer-jobs-task"></a><span data-ttu-id="5cc28-102">Aufträge übertragen (Task)</span><span class="sxs-lookup"><span data-stu-id="5cc28-102">Transfer Jobs Task</span></span>
  <span data-ttu-id="5cc28-103">Durch die Task "Aufträge übertragen" werden ein oder mehrere Aufträge des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents zwischen Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]übertragen.</span><span class="sxs-lookup"><span data-stu-id="5cc28-103">The Transfer Jobs task transfers one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5cc28-104">Der Task Aufträge übertragen kann so konfiguriert werden, dass alle Aufträge oder nur bestimmte Aufträge übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="5cc28-104">The Transfer Jobs task can be configured to transfer all jobs, or only specified jobs.</span></span> <span data-ttu-id="5cc28-105">Sie können auch angeben, ob die übertragenen Aufträge auf dem Ziel aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5cc28-105">You can also indicate whether the transferred jobs are enabled at the destination.</span></span>  
  
 <span data-ttu-id="5cc28-106">Die zu übertragenden Aufträge sind auf dem Ziel möglicherweise schon vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5cc28-106">The jobs to be transferred may already exist on the destination.</span></span> <span data-ttu-id="5cc28-107">Es gibt folgende Möglichkeiten, um den Task Aufträge übertragen so zu konfigurieren, dass bereits vorhandene Aufträge behandelt werden:</span><span class="sxs-lookup"><span data-stu-id="5cc28-107">The Transfer Jobs task can be configured to handle existing jobs in the following ways:</span></span>  
  
-   <span data-ttu-id="5cc28-108">Vorhandene Aufträge werden überschrieben.</span><span class="sxs-lookup"><span data-stu-id="5cc28-108">Overwrite existing jobs.</span></span>  
  
-   <span data-ttu-id="5cc28-109">Der Auftrag erzeugt einen Fehler, wenn doppelte Aufträge vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="5cc28-109">Fail the task when duplicate jobs exist.</span></span>  
  
-   <span data-ttu-id="5cc28-110">Doppelte Aufträge werden ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="5cc28-110">Skip duplicate jobs.</span></span>  
  
 <span data-ttu-id="5cc28-111">Zur Laufzeit stellt der Task Aufträge übertragen mithilfe eines oder zweier SMO-Verbindungs-Manager eine Verbindung mit dem Quell- und Zielserver her.</span><span class="sxs-lookup"><span data-stu-id="5cc28-111">At run time, the Transfer Jobs task connects to the source and destination servers by using one or two SMO connection managers.</span></span> <span data-ttu-id="5cc28-112">Der SMO-Verbindungs-Manager wird unabhängig vom Task Aufträge übertragen konfiguriert, und im Task Aufträge übertragen wird dann darauf verwiesen.</span><span class="sxs-lookup"><span data-stu-id="5cc28-112">The SMO connection manager is configured separately from the Transfer Jobs task, and then is referenced in the Transfer Jobs task.</span></span> <span data-ttu-id="5cc28-113">Im SMO-Verbindungs-Manager wird der Server sowie der für den Zugriff auf den Server zu verwendende Authentifizierungsmodus angegeben.</span><span class="sxs-lookup"><span data-stu-id="5cc28-113">The SMO connection manager specifies the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="5cc28-114">Weitere Informationen finden Sie unter [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5cc28-114">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
## <a name="transferring-jobs-between-instances-of-sql-server"></a><span data-ttu-id="5cc28-115">Übertragen von Aufträgen zwischen Instanzen von SQL Server</span><span class="sxs-lookup"><span data-stu-id="5cc28-115">Transferring Jobs Between Instances of SQL Server</span></span>  
 <span data-ttu-id="5cc28-116">Die Task "Aufträge übertragen" unterstützt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Quellen und -Ziele.</span><span class="sxs-lookup"><span data-stu-id="5cc28-116">The Transfer Jobs task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span> <span data-ttu-id="5cc28-117">Es gibt keinerlei Beschränkungen, welche Version Sie als Quelle oder Ziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="5cc28-117">There are no restrictions on which version to use as a source or destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="5cc28-118">Events</span><span class="sxs-lookup"><span data-stu-id="5cc28-118">Events</span></span>  
 <span data-ttu-id="5cc28-119">Der Task Aufträge übertragen löst ein Informationsereignis aus, in dem die Anzahl der übertragenen Aufträge angegeben ist, und ein Warnungsereignis, wenn ein Auftrag überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="5cc28-119">The Transfer Jobs task raises an information event that reports the number of jobs transferred and a warning event when a job is overwritten.</span></span> <span data-ttu-id="5cc28-120">Während der Auftrag übertragen wird, werden keine Angaben zum Fortschritt des Vorgangs gemacht – es wird lediglich 0 % und bei Abschluss 100 % angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5cc28-120">The task does not report incremental progress of the job transfer; it reports only 0% and 100% completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="5cc28-121">Ausführungswert</span><span class="sxs-lookup"><span data-stu-id="5cc28-121">Execution Value</span></span>  
 <span data-ttu-id="5cc28-122">Der in der `ExecutionValue`-Eigenschaft des Tasks definierte Ausführungswert gibt die Anzahl der zu übertragenden Aufträge zurück.</span><span class="sxs-lookup"><span data-stu-id="5cc28-122">The execution value, defined in the `ExecutionValue` property of the task, returns the number of jobs that are transferred.</span></span> <span data-ttu-id="5cc28-123">Mithilfe einer benutzerdefinierten Variable, die der `ExecValueVariable`-Eigenschaft des Tasks Aufträge übertragen zugewiesen wird, können Informationen zur Auftragsübertragung für andere Objekte des Pakets verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="5cc28-123">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Jobs task, information about the job transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="5cc28-124">Weitere Informationen finden Sie unter [Integration Services-Variablen &#40;SSIS&#41;](../integration-services-ssis-variables.md) und [Verwenden von Variablen in Paketen](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="5cc28-124">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="5cc28-125">Protokolleinträge</span><span class="sxs-lookup"><span data-stu-id="5cc28-125">Log Entries</span></span>  
 <span data-ttu-id="5cc28-126">Der Task Aufträge übertragen enthält die folgenden benutzerdefinierten Protokolleinträge:</span><span class="sxs-lookup"><span data-stu-id="5cc28-126">The Transfer Jobs task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="5cc28-127">TransferJobsTaskStarTransferringObjects   Dieser Protokolleintrag gibt an, dass die Übertragung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="5cc28-127">TransferJobsTaskStarTransferringObjects   This log entry reports that the transfer has started.</span></span> <span data-ttu-id="5cc28-128">Der Protokolleintrag enthält die Startzeit.</span><span class="sxs-lookup"><span data-stu-id="5cc28-128">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="5cc28-129">TransferJobsTaskFinishedTransferringObjects    Dieser Protokolleintrag gibt an, dass die Übertragung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="5cc28-129">TransferJobsTaskFinishedTransferringObjects    This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="5cc28-130">Der Protokolleintrag enthält die Beendigungszeit.</span><span class="sxs-lookup"><span data-stu-id="5cc28-130">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="5cc28-131">Außerdem gibt ein Protokolleintrag für das `OnInformation`-Ereignis die Anzahl der übertragenen Aufträge an. Schließlich wird ein Protokolleintrag für das `OnWarning`-Ereignis für jeden auf dem Ziel überschriebenen Auftrag erstellt.</span><span class="sxs-lookup"><span data-stu-id="5cc28-131">In addition, a log entry for the `OnInformation` event reports the number of jobs that were transferred and a log entry for the `OnWarning` event is written for each job on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="5cc28-132">Sicherheit und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5cc28-132">Security and Permissions</span></span>  
 <span data-ttu-id="5cc28-133">Zum Übertragen von Aufträgen muss der Benutzer sowohl in der Quell- als auch in der Zielinstanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ein Mitglied der festen Serverrolle sysadmin oder einer der festen Datenbankrollen für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent der msdb-Datenbank sein.</span><span class="sxs-lookup"><span data-stu-id="5cc28-133">To transfer jobs, the user must be a member of the sysadmin fixed server role or one of the fixed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles on the msdb database on the both the source and destination instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="configuration-of-the-transfer-jobs-task"></a><span data-ttu-id="5cc28-134">Konfiguration des Tasks "Aufträge übertragen"</span><span class="sxs-lookup"><span data-stu-id="5cc28-134">Configuration of the Transfer Jobs Task</span></span>  
 <span data-ttu-id="5cc28-135">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="5cc28-135">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="5cc28-136">Klicken Sie auf eines der folgenden Themen, um Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="5cc28-136">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="5cc28-137">Editor für den Task Aufträge übertragen &#40;Seite Allgemein&#41;</span><span class="sxs-lookup"><span data-stu-id="5cc28-137">Transfer Jobs Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="5cc28-138">Editor für den Task Aufträge übertragen &#40;Seite Aufträge&#41;</span><span class="sxs-lookup"><span data-stu-id="5cc28-138">Transfer Jobs Task Editor &#40;Jobs Page&#41;</span></span>](../transfer-jobs-task-editor-jobs-page.md)  
  
-   [<span data-ttu-id="5cc28-139">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="5cc28-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="5cc28-140">Klicken Sie auf folgendes Thema, um weitere Informationen zum programmgesteuerten Festlegen dieser Eigenschaften zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="5cc28-140">For information about programmatically setting these properties, click the of the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferJobsTask.TransferJobsTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="5cc28-141">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="5cc28-141">Related Tasks</span></span>  
 <span data-ttu-id="5cc28-142">Klicken Sie auf das folgende Thema, um weitere Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="5cc28-142">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="5cc28-143">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="5cc28-143">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="5cc28-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5cc28-144">See Also</span></span>  
 <span data-ttu-id="5cc28-145">[Integration Services-Tasks](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="5cc28-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="5cc28-146">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="5cc28-146">Control Flow</span></span>](control-flow.md)  
  
  
