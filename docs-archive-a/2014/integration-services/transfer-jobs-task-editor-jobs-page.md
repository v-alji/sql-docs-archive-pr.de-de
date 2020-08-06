---
title: Editor für den Task Aufträge übertragen (Seite Aufträge) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferjobstask.jobs.f1
helpviewer_keywords:
- Transfer Jobs Task Editor
ms.assetid: e72b1dc7-8cda-4ee6-abb5-d438370f04df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d2d506da6997965e40d66521f7dccb8218e165fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630711"
---
# <a name="transfer-jobs-task-editor-jobs-page"></a><span data-ttu-id="c960e-102">Editor für den Task Aufträge übertragen (Seite Aufträge)</span><span class="sxs-lookup"><span data-stu-id="c960e-102">Transfer Jobs Task Editor (Jobs Page)</span></span>
  <span data-ttu-id="c960e-103">Auf der Seite **Aufträge** des Dialogfelds **Editor für den Task "Aufträge übertragen"** können Sie die Eigenschaften für das Kopieren von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agentaufträgen von einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in eine andere angeben.</span><span class="sxs-lookup"><span data-stu-id="c960e-103">Use the **Jobs** page of the **Transfer Jobs Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="c960e-104">Weitere Informationen zum Task Aufträge übertragen finden Sie unter [Transfer Jobs Task](control-flow/transfer-jobs-task.md).</span><span class="sxs-lookup"><span data-stu-id="c960e-104">For more information about the Transfer Jobs task, see [Transfer Jobs Task](control-flow/transfer-jobs-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c960e-105">Um auf dem Quellserver auf Aufträge zuzugreifen, müssen Benutzer auf dem Server Mitglied mindestens einer festen Serverrolle **SQLAgentUserRole** sein.</span><span class="sxs-lookup"><span data-stu-id="c960e-105">To access jobs on the source server, users must be a member of at least the **SQLAgentUserRole** fixed database role on the server.</span></span> <span data-ttu-id="c960e-106">Um auf dem Zielserver Aufträge erfolgreich zu erstellen, muss der Benutzer Mitglied der festen Datenbankrolle **sysadmin** oder einer der festen Datenbankrollen des [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agents sein.</span><span class="sxs-lookup"><span data-stu-id="c960e-106">To successfully create jobs on the destination server, the user must be a member of the **sysadmin** fixed server role or one of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles.</span></span> <span data-ttu-id="c960e-107">Weitere Informationen zu den festen Datenbankrollen des [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agents und zu deren Berechtigungen finden Sie unter [Feste Datenbankrollen des SQL Server-Agents](../ssms/agent/sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c960e-107">For more information about [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles and their permissions, see [SQL Server Agent Fixed Database Roles](../ssms/agent/sql-server-agent-fixed-database-roles.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c960e-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c960e-108">Options</span></span>  
 <span data-ttu-id="c960e-109">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="c960e-109">**SourceConnection**</span></span>  
 <span data-ttu-id="c960e-110">Wählen Sie in der Liste einen SMO-Verbindungs-Manager aus, oder klicken Sie auf **\<New connection...>** , um eine neue Verbindung mit dem Quellserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c960e-110">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="c960e-111">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="c960e-111">**DestinationConnection**</span></span>  
 <span data-ttu-id="c960e-112">Wählen Sie in der Liste einen SMO-Verbindungs-Manager aus, oder klicken Sie auf **\<New connection...>** , um eine neue Verbindung mit dem Zielserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c960e-112">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="c960e-113">**TransferAllJobs**</span><span class="sxs-lookup"><span data-stu-id="c960e-113">**TransferAllJobs**</span></span>  
 <span data-ttu-id="c960e-114">Wählen Sie aus, ob der Task alle oder nur angegebene [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agentaufträge vom Quell- auf den Zielserver kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="c960e-114">Select whether the task should copy all or only the specified [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs from the source to the destination server.</span></span>  
  
 <span data-ttu-id="c960e-115">Für diese Eigenschaft sind die in der folgenden Tabelle aufgeführten Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="c960e-115">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="c960e-116">Wert</span><span class="sxs-lookup"><span data-stu-id="c960e-116">Value</span></span>|<span data-ttu-id="c960e-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c960e-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c960e-118">**True**</span><span class="sxs-lookup"><span data-stu-id="c960e-118">**True**</span></span>|<span data-ttu-id="c960e-119">Kopiert alle Aufträge.</span><span class="sxs-lookup"><span data-stu-id="c960e-119">Copy all jobs.</span></span>|  
|<span data-ttu-id="c960e-120">**False**</span><span class="sxs-lookup"><span data-stu-id="c960e-120">**False**</span></span>|<span data-ttu-id="c960e-121">Kopiert nur angegebene Aufträge.</span><span class="sxs-lookup"><span data-stu-id="c960e-121">Copy only the specified jobs.</span></span>|  
  
 <span data-ttu-id="c960e-122">**JobsList**</span><span class="sxs-lookup"><span data-stu-id="c960e-122">**JobsList**</span></span>  
 <span data-ttu-id="c960e-123">Klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** , um die zu kopierenden Aufträge auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c960e-123">Click the browse button **(...)** to select the jobs to copy.</span></span> <span data-ttu-id="c960e-124">Es muss mindestens ein Auftrag ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="c960e-124">At least one job must be selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c960e-125">Geben Sie vor der Auswahl der zu kopierenden Aufträge **SourceConnection** an.</span><span class="sxs-lookup"><span data-stu-id="c960e-125">Specify the **SourceConnection** before selecting jobs to copy.</span></span>  
  
 <span data-ttu-id="c960e-126">Die Option **JobsList** ist nicht verfügbar, wenn **TransferAllJobs** auf **True**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c960e-126">The **JobsList** option is unavailable when **TransferAllJobs** is set to **True**.</span></span>  
  
 <span data-ttu-id="c960e-127">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="c960e-127">**IfObjectExists**</span></span>  
 <span data-ttu-id="c960e-128">Wählen Sie aus, wie der Task Aufträge behandeln soll, die auf dem Zielserver bereits mit demselben Namen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c960e-128">Select how the task should handle jobs of the same name that already exist on the destination server.</span></span>  
  
 <span data-ttu-id="c960e-129">Für diese Eigenschaft sind die in der folgenden Tabelle aufgeführten Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="c960e-129">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="c960e-130">Wert</span><span class="sxs-lookup"><span data-stu-id="c960e-130">Value</span></span>|<span data-ttu-id="c960e-131">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c960e-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c960e-132">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="c960e-132">**FailTask**</span></span>|<span data-ttu-id="c960e-133">Der Task schlägt fehl, wenn auf dem Zielserver bereits Aufträge mit demselben Namen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c960e-133">Task fails if jobs of the same name already exist on the destination server.</span></span>|  
|<span data-ttu-id="c960e-134">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="c960e-134">**Overwrite**</span></span>|<span data-ttu-id="c960e-135">Der Task überschreibt auf dem Zielserver Aufträge mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="c960e-135">Task overwrites jobs of the same name on the destination server.</span></span>|  
|<span data-ttu-id="c960e-136">**Skip**</span><span class="sxs-lookup"><span data-stu-id="c960e-136">**Skip**</span></span>|<span data-ttu-id="c960e-137">Der Task lässt Aufträge aus, die auf dem Zielserver mit demselben Namen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c960e-137">Task skips jobs of the same name that exist on the destination server.</span></span>|  
  
 <span data-ttu-id="c960e-138">**EnableJobsAtDestination**</span><span class="sxs-lookup"><span data-stu-id="c960e-138">**EnableJobsAtDestination**</span></span>  
 <span data-ttu-id="c960e-139">Wählen Sie aus, ob die auf den Zielserver kopierten Aufträge aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c960e-139">Select whether the jobs copied to the destination server should be enabled.</span></span>  
  
 <span data-ttu-id="c960e-140">Für diese Eigenschaft sind die in der folgenden Tabelle aufgeführten Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="c960e-140">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="c960e-141">Wert</span><span class="sxs-lookup"><span data-stu-id="c960e-141">Value</span></span>|<span data-ttu-id="c960e-142">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c960e-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c960e-143">**True**</span><span class="sxs-lookup"><span data-stu-id="c960e-143">**True**</span></span>|<span data-ttu-id="c960e-144">Aktiviert Jobs auf dem Zielserver.</span><span class="sxs-lookup"><span data-stu-id="c960e-144">Enable jobs on destination server.</span></span>|  
|<span data-ttu-id="c960e-145">**False**</span><span class="sxs-lookup"><span data-stu-id="c960e-145">**False**</span></span>|<span data-ttu-id="c960e-146">Deaktiviert Jobs auf dem Zielserver.</span><span class="sxs-lookup"><span data-stu-id="c960e-146">Disable jobs on destination server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c960e-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c960e-147">See Also</span></span>  
 <span data-ttu-id="c960e-148">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c960e-148">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="c960e-149">[Integration Services-Tasks](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="c960e-149">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="c960e-150">[Editor für den Task Aufträge übertragen &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="c960e-150">[Transfer Jobs Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="c960e-151">[Seite Ausdrücke](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="c960e-151">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="c960e-152">SMO-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="c960e-152">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
