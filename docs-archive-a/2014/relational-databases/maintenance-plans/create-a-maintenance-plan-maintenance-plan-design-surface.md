---
title: Erstellen eines Wartungsplans (Entwurfsoberfläche für Wartungspläne) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Maintenance Plan Design Surface
ms.assetid: 2ef803ee-a9f8-454a-ad63-fedcbe6838d1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 77e347720824198ba7d6abaddedd7a581ace98a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620359"
---
# <a name="create-a-maintenance-plan-maintenance-plan-design-surface"></a><span data-ttu-id="46be2-102">Erstellen eines Wartungsplans (Entwurfsoberfläche für Wartungspläne)</span><span class="sxs-lookup"><span data-stu-id="46be2-102">Create a Maintenance Plan (Maintenance Plan Design Surface)</span></span>
  <span data-ttu-id="46be2-103">In diesem Thema wird beschrieben, wie für einen einzelnen Server oder mehrere Server mithilfe der Entwurfsoberfläche für Wartungspläne in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]ein Wartungsplan erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="46be2-103">This topic describes how to create a single server or multiserver maintenance plan using the Maintenance Plan Design Surface in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="46be2-104">Der **Wartungsplanungs-Assistent** eignet sich am besten für das Erstellen von grundlegenden Wartungsplänen. Wenn Sie die Entwurfsoberfläche zum Erstellen eines Plans verwenden, können Sie einen erweiterten Workflow nutzen.</span><span class="sxs-lookup"><span data-stu-id="46be2-104">While the **Maintenance Plan Wizard** is best for creating basic maintenance plans, creating a plan using the design surface allows you to utilize enhanced workflow.</span></span>  
  
 <span data-ttu-id="46be2-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="46be2-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="46be2-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="46be2-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="46be2-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="46be2-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="46be2-108">Security</span><span class="sxs-lookup"><span data-stu-id="46be2-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="46be2-109">Erstellen eines Wartungsplans mithilfe der Entwurfsoberfläche für Wartungspläne</span><span class="sxs-lookup"><span data-stu-id="46be2-109">Creating a maintenance plan using the Maintenance Plan Design Surface</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="46be2-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="46be2-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="46be2-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="46be2-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="46be2-112">Wenn Sie einen Multiserver-Wartungsplan erstellen möchten, muss eine Multiserverumgebung mit einem Masterserver und mindestens einem Zielserver konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="46be2-112">To create a multiserver maintenance plan, a multiserver environment containing one master server and one or more target servers must be configured.</span></span> <span data-ttu-id="46be2-113">Multiserver-Wartungspläne müssen auf dem Masterserver erstellt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="46be2-113">Multiserver maintenance plans must be created and maintained on the master server.</span></span> <span data-ttu-id="46be2-114">Diese Pläne können auf Zielservern zwar angezeigt, jedoch nicht verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="46be2-114">These plans can be viewed, but not maintained, on target servers.</span></span>  
  
-   <span data-ttu-id="46be2-115">Mitglieder der **db_ssisadmin** -Rolle und der **dc_admin** -Rolle können ihre Berechtigungen möglicherweise auf **sysadmin**erhöhen.</span><span class="sxs-lookup"><span data-stu-id="46be2-115">Members of the **db_ssisadmin** and **dc_admin** roles may be able to elevate their privileges to **sysadmin**.</span></span> <span data-ttu-id="46be2-116">Diese Ausweitung von Berechtigungen ist möglich, da diese Rollen [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Pakete ändern können. Diese Pakete können von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe des **sysadmin** -Sicherheitskontexts des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="46be2-116">This elevation of privilege can occur because these roles can modify [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages; these packages can be executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the **sysadmin** security context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="46be2-117">Konfigurieren Sie als Schutz vor dieser Ausweitung von Berechtigungen beim Ausführen von Wartungsplänen, Datensammlungssätzen und anderen [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paketen Aufträge des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents, die Pakete ausführen, für die Verwendung eines Proxykontos mit eingeschränkten Berechtigungen, oder fügen Sie der **db_ssisadmin** -Rolle und der **dc_admin** -Rolle nur **sysadmin** -Mitglieder hinzu.</span><span class="sxs-lookup"><span data-stu-id="46be2-117">To guard against this elevation of privilege when running maintenance plans, data collection sets, and other [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs that run packages to use a proxy account with limited privileges or only add **sysadmin** members to the **db_ssisadmin** and **dc_admin** roles.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="46be2-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="46be2-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="46be2-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="46be2-119">Permissions</span></span>  
 <span data-ttu-id="46be2-120">Sie müssen Mitglied der festen Serverrolle **sysadmin** sein, um Wartungspläne erstellen oder verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="46be2-120">To create or manage maintenance plans, you must be a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="46be2-121">Im Objekt-Explorer wird der **Wartungspläne** -Knoten nur für Benutzer angezeigt, die Mitglied der festen Serverrolle **sysadmin** sind.</span><span class="sxs-lookup"><span data-stu-id="46be2-121">Object Explorer only displays the **Maintenance Plans** node for users who are members of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-maintenance-plan-design-surface"></a><a name="SSMSProcedure"></a> <span data-ttu-id="46be2-122">Verwendung der Entwurfsoberfläche für Wartungspläne</span><span class="sxs-lookup"><span data-stu-id="46be2-122">Using Maintenance Plan Design Surface</span></span>  
  
#### <a name="to-create-a-maintenance-plan"></a><span data-ttu-id="46be2-123">So erstellen Sie einen Wartungsplan</span><span class="sxs-lookup"><span data-stu-id="46be2-123">To create a maintenance plan</span></span>  
  
1.  <span data-ttu-id="46be2-124">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um den Server zu erweitern, auf dem Sie einen Wartungsplan erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="46be2-124">In Object Explorer, click the plus sign to expand the server where you want to create a maintenance plan.</span></span>  
  
2.  <span data-ttu-id="46be2-125">Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="46be2-125">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="46be2-126">Klicken Sie mit der rechten Maustaste auf den Ordner **Wartungspläne** , und wählen Sie **Neuer Wartungsplan**aus.</span><span class="sxs-lookup"><span data-stu-id="46be2-126">Right-click the **Maintenance Plans** folder and select **New Maintenance Plan**.</span></span>  
  
4.  <span data-ttu-id="46be2-127">Geben Sie im Dialogfeld **Neuer Wartungsplan** im Feld **Name** einen Namen für den Plan ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="46be2-127">In the **New Maintenance Plan** dialog box, in the **Name** box, type a name for the plan and click **OK**.</span></span> <span data-ttu-id="46be2-128">Dadurch werden die Toolbox und die Oberfläche _maintenance_plan_name_ **[Design]** mit dem Unterplan **Subplan_1** geöffnet, der im Hauptraster erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="46be2-128">This opens the  Toolbox and the _maintenance_plan_name_ **[Design]** surface with the **Subplan_1** subplan created in the main grid.</span></span>  
  
     <span data-ttu-id="46be2-129">Die folgenden Optionen sind in der Kopfzeile des Entwurfsbereichs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="46be2-129">The following options are available in the design space's header.</span></span>  
  
     <span data-ttu-id="46be2-130">**Unterplan hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="46be2-130">**Add Subplan**</span></span>  
     <span data-ttu-id="46be2-131">Mit dieser Option fügen Sie einen Unterplan hinzu, den Sie konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="46be2-131">Adds a subplan that you can configure.</span></span>  
  
     <span data-ttu-id="46be2-132">**Unterplaneigenschaften**</span><span class="sxs-lookup"><span data-stu-id="46be2-132">**Subplan Properties**</span></span>  
     <span data-ttu-id="46be2-133">Zeigt das Dialogfeld **Unterplaneigenschaften** für den ausgewählten Unterplan im Hauptraster an.</span><span class="sxs-lookup"><span data-stu-id="46be2-133">Displays the **Subplan Properties** dialog box for the selected subplan in the main grid.</span></span> <span data-ttu-id="46be2-134">Sie können im Raster auch auf einen Unterplan doppelklicken, um das Dialogfeld **Unterplaneigenschaften** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="46be2-134">Alternately, double-click a subplan in the grid to display the **Subplan Properties** dialog box.</span></span> <span data-ttu-id="46be2-135">Weitere Informationen zu diesem Dialogfeld finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="46be2-135">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="46be2-136">**Ausgewählten Unterplan löschen**</span><span class="sxs-lookup"><span data-stu-id="46be2-136">**Delete Selected Subplan**</span></span>  
     <span data-ttu-id="46be2-137">Hiermit löschen Sie den ausgewählten Unterplan.</span><span class="sxs-lookup"><span data-stu-id="46be2-137">Deletes the selected subplan.</span></span>  
  
     <span data-ttu-id="46be2-138">**Zeitplan des Unterplans**</span><span class="sxs-lookup"><span data-stu-id="46be2-138">**Subplan Schedule**</span></span>  
     <span data-ttu-id="46be2-139">Zeigt das Dialogfeld **Neuer Auftragszeitplan** für den ausgewählten Unterplan an.</span><span class="sxs-lookup"><span data-stu-id="46be2-139">Displays the **New Job Schedule** dialog box for the selected subplan.</span></span>  
  
     <span data-ttu-id="46be2-140">**Zeitplan entfernen**</span><span class="sxs-lookup"><span data-stu-id="46be2-140">**Remove Schedule**</span></span>  
     <span data-ttu-id="46be2-141">Mit dieser Option entfernen Sie einen Zeitplan aus dem ausgewählten Unterplan.</span><span class="sxs-lookup"><span data-stu-id="46be2-141">Removes a schedule from the selected subplan.</span></span>  
  
     <span data-ttu-id="46be2-142">**Verwalten von Verbindungen**</span><span class="sxs-lookup"><span data-stu-id="46be2-142">**Manage Connections**</span></span>  
     <span data-ttu-id="46be2-143">Hiermit zeigen Sie das Dialogfeld **Verbindungen verwalten** an.</span><span class="sxs-lookup"><span data-stu-id="46be2-143">Displays the **Manage Connections** dialog box.</span></span> <span data-ttu-id="46be2-144">Es wird verwendet, um dem Wartungsplan zusätzliche [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzverbindungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="46be2-144">Used to add additional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance connections to the maintenance plan.</span></span> <span data-ttu-id="46be2-145">Weitere Informationen zu diesem Dialogfeld finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="46be2-145">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="46be2-146">**Berichterstellung und Protokollierung**</span><span class="sxs-lookup"><span data-stu-id="46be2-146">**Reporting and Logging**</span></span>  
     <span data-ttu-id="46be2-147">Zeigt das Dialogfeld **Berichterstellung und Protokollierung** an.</span><span class="sxs-lookup"><span data-stu-id="46be2-147">Displays the **Reporting and Logging** dialog box.</span></span> <span data-ttu-id="46be2-148">Weitere Informationen zu diesem Dialogfeld finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="46be2-148">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="46be2-149">**Server**</span><span class="sxs-lookup"><span data-stu-id="46be2-149">**Servers**</span></span>  
     <span data-ttu-id="46be2-150">Mit dieser Option zeigen Sie das Dialogfeld **Server** an, das zum Auswählen der Server verwendet wird, auf denen die Unterplantasks ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="46be2-150">Display the **Servers** dialog box, which is used to select the servers where the subplan tasks will be run.</span></span> <span data-ttu-id="46be2-151">Diese Option ist nur auf Masterservern in Umgebungen mit mehreren Servern aktiviert.</span><span class="sxs-lookup"><span data-stu-id="46be2-151">This option is enabled only on master servers in multiserver environments.</span></span> <span data-ttu-id="46be2-152">Weitere Informationen finden Sie unter [Erstellen einer Multiserverumgebung](../../ssms/agent/create-a-multiserver-environment.md) und [Wartungsplan &#40;Servers&#41;](maintenance-plan-servers.md).</span><span class="sxs-lookup"><span data-stu-id="46be2-152">For more information, see [Create a Multiserver Environment](../../ssms/agent/create-a-multiserver-environment.md) and [Maintenance Plan &#40;Servers&#41;](maintenance-plan-servers.md).</span></span>  
  
     <span data-ttu-id="46be2-153">**Name**</span><span class="sxs-lookup"><span data-stu-id="46be2-153">**Name**</span></span>  
     <span data-ttu-id="46be2-154">Hier zeigen Sie den Namen für den Wartungsplan an.</span><span class="sxs-lookup"><span data-stu-id="46be2-154">Display the maintenance plan name.</span></span> <span data-ttu-id="46be2-155">Bei neuen Wartungsplänen wird der Name in einem Dialogfeld angegeben, bevor der Designer für den Wartungsplan geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="46be2-155">For new maintenance plans, the name is specified in a dialog box before the maintenance plan designer opens.</span></span> <span data-ttu-id="46be2-156">Wenn Sie einen Wartungsplan umbenennen möchten, klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Plan, und klicken Sie anschließend auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="46be2-156">To rename a maintenance plan, right-click the plan in Object Explorer, and then click **Rename**.</span></span>  
  
     <span data-ttu-id="46be2-157">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="46be2-157">**Description**</span></span>  
     <span data-ttu-id="46be2-158">Hier können Sie eine Beschreibung für den Wartungsplan anzeigen oder festlegen.</span><span class="sxs-lookup"><span data-stu-id="46be2-158">View or specify a description for the maintenance plan.</span></span> <span data-ttu-id="46be2-159">Die maximale Länge für eine Beschreibung beträgt 512 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="46be2-159">The maximum length for a description is 512 characters.</span></span>  
  
     <span data-ttu-id="46be2-160">**Designeroberfläche**</span><span class="sxs-lookup"><span data-stu-id="46be2-160">**Designer Surface**</span></span>  
     <span data-ttu-id="46be2-161">Hiermit können Sie Wartungspläne entwerfen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="46be2-161">Design and maintain maintenance plans.</span></span> <span data-ttu-id="46be2-162">Verwenden Sie die Designeroberfläche, um einem Plan Wartungspläne hinzuzufügen, Tasks aus einem Plan zu entfernen, Rangfolgenlinks zwischen den Tasks anzugeben oder Taskverzweigungen und -parallelausführungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="46be2-162">Use the designer surface to add maintenance tasks to a plan, remove tasks from a plan, specify precedence links between the tasks, and indicate task branching and parallelism.</span></span>  
  
     <span data-ttu-id="46be2-163">Ein Rangfolgenlink zwischen zwei Tasks legt eine Beziehung zwischen den Tasks fest.</span><span class="sxs-lookup"><span data-stu-id="46be2-163">A precedence link between two tasks establishes a relationship between the tasks.</span></span> <span data-ttu-id="46be2-164">Der zweite Task (der *abhängige Task*) wird nur ausgeführt, wenn das Ausführungsergebnis des ersten Tasks (des *Vorgängertasks*) bestimmte Kriterien erfüllt.</span><span class="sxs-lookup"><span data-stu-id="46be2-164">The second task (the *dependent task*) executes only if the execution result of the first task (the *precedent task*) matches specified criteria.</span></span> <span data-ttu-id="46be2-165">Normalerweise ist das angegebene Ausführungsergebnis **Erfolg**, **Fehler**oder **Beendigung**.</span><span class="sxs-lookup"><span data-stu-id="46be2-165">Typically the execution result specified is **Success**, **Failure**, or **Completion**.</span></span> <span data-ttu-id="46be2-166">Weitere Informationen finden Sie unter Schritt **8** .</span><span class="sxs-lookup"><span data-stu-id="46be2-166">For more information, see step **8** below.</span></span>  
  
5.  <span data-ttu-id="46be2-167">Doppelklicken Sie in der Kopfzeile des Entwurfsbereichs auf **Unterplan_1** , und geben Sie im Dialogfeld **Unterplaneigenschaften** einen Namen sowie eine Beschreibung für den Unterplan ein.</span><span class="sxs-lookup"><span data-stu-id="46be2-167">In the design space's header, double-click **Subplan_1** and enter a name and description for the subplan in the **Subplan Properties** dialog box.</span></span>  
  
     <span data-ttu-id="46be2-168">Die folgenden Optionen sind im Dialogfeld **Unterplaneigenschaften** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="46be2-168">The following options are available in the **Subplan Properties** dialog box.</span></span>  
  
     <span data-ttu-id="46be2-169">**Name**</span><span class="sxs-lookup"><span data-stu-id="46be2-169">**Name**</span></span>  
     <span data-ttu-id="46be2-170">Der Name des Unterplans.</span><span class="sxs-lookup"><span data-stu-id="46be2-170">The name of the subplan.</span></span>  
  
     <span data-ttu-id="46be2-171">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="46be2-171">**Description**</span></span>  
     <span data-ttu-id="46be2-172">Kurze Beschreibung des Unterplans.</span><span class="sxs-lookup"><span data-stu-id="46be2-172">A brief description of the subplan.</span></span>  
  
     <span data-ttu-id="46be2-173">**Zeitplan**</span><span class="sxs-lookup"><span data-stu-id="46be2-173">**Schedule**</span></span>  
     <span data-ttu-id="46be2-174">Gibt an, nach welchem Zeitplan der Unterplan ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="46be2-174">Indicates on what schedule the subplan will be run.</span></span> <span data-ttu-id="46be2-175">Klicken Sie auf **Zeitplan des Unterplans** , um das Dialogfeld **Neuer Auftragszeitplan** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="46be2-175">Click **Subplan Schedule** to open the **New Job Schedule** dialog box.</span></span> <span data-ttu-id="46be2-176">Klicken Sie auf **Zeitplan entfernen** , um den Zeitplan aus dem Unterplan zu löschen.</span><span class="sxs-lookup"><span data-stu-id="46be2-176">Click **Remove Schedule** to delete the schedule from the subplan.</span></span>  
  
     <span data-ttu-id="46be2-177">Liste**Ausführen als**</span><span class="sxs-lookup"><span data-stu-id="46be2-177">**Run as** list</span></span>  
     <span data-ttu-id="46be2-178">Wählen Sie das Konto aus, das zum Ausführen dieser Unteraufgabe verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="46be2-178">Select the account to use to run this subtask.</span></span>  
  
6.  <span data-ttu-id="46be2-179">Klicken Sie auf **Zeitplan des Unterplans** , um die Details zum Zeitplan in das Dialogfeld **Neuer Auftragszeitplan** einzugeben.</span><span class="sxs-lookup"><span data-stu-id="46be2-179">Click **Subplan Schedule** to enter schedule details in the **New Job Schedule** dialog box.</span></span>  
  
7.  <span data-ttu-id="46be2-180">Um den Unterplan zu erstellen, ziehen Sie die Tasksteuerungselemente aus der **Toolbox** auf die Planentwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="46be2-180">To build the subplan, drag and drop task flow elements from the **Toolbox** to the plan design surface.</span></span> <span data-ttu-id="46be2-181">Doppelklicken Sie auf Tasks, um Dialogfelder zum Konfigurieren der Taskoptionen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="46be2-181">Double-click tasks to open dialog boxes to configure the task options.</span></span>  
  
     <span data-ttu-id="46be2-182">Die folgenden Wartungsplantasks sind in der **Toolbox**verfügbar:</span><span class="sxs-lookup"><span data-stu-id="46be2-182">The following maintenance plan tasks are available in the **Toolbox**:</span></span>  
  
    -   <span data-ttu-id="46be2-183">**Datenbank sichern (Task)**</span><span class="sxs-lookup"><span data-stu-id="46be2-183">**Back up Database Task**</span></span>  
  
    -   <span data-ttu-id="46be2-184">**Datenbankintegrität überprüfen (Task)**</span><span class="sxs-lookup"><span data-stu-id="46be2-184">**Check Database Integrity Task**</span></span>  
  
    -   <span data-ttu-id="46be2-185">**Auftrag des SQL Server-Agents ausführen (Task)**</span><span class="sxs-lookup"><span data-stu-id="46be2-185">**Execute SQL Server Agent Job Task**</span></span>  
  
    -   <span data-ttu-id="46be2-186">**T-SQL-Anweisung ausführen (Task)**</span><span class="sxs-lookup"><span data-stu-id="46be2-186">**Execute T-SQL Statement Task**</span></span>  
  
    -   <span data-ttu-id="46be2-187">**Verlaufscleanup (Task)**</span><span class="sxs-lookup"><span data-stu-id="46be2-187">**History Cleanup Task**</span></span>  
  
    -   <span data-ttu-id="46be2-188">**Wartungscleanup (Task)**</span><span class="sxs-lookup"><span data-stu-id="46be2-188">**Maintenance Cleanup Task**</span></span>  
  
    -   <span data-ttu-id="46be2-189">**Operator benachrichtigen (Task)**</span><span class="sxs-lookup"><span data-stu-id="46be2-189">**Notify Operator Task**</span></span>  
  
    -   <span data-ttu-id="46be2-190">**Index neu erstellen (Task)**</span><span class="sxs-lookup"><span data-stu-id="46be2-190">**Rebuild Index Task**</span></span>  
  
    -   <span data-ttu-id="46be2-191">**Index neu organisieren (Task)**</span><span class="sxs-lookup"><span data-stu-id="46be2-191">**Reorganize Index Task**</span></span>  
  
    -   <span data-ttu-id="46be2-192">**Datenbank verkleinern (Task)**</span><span class="sxs-lookup"><span data-stu-id="46be2-192">**Shrink Database Task**</span></span>  
  
    -   <span data-ttu-id="46be2-193">**Statistiken aktualisieren (Task)**</span><span class="sxs-lookup"><span data-stu-id="46be2-193">**Update Statistics Task**</span></span>  
  
     <span data-ttu-id="46be2-194">So fügen Sie der **Toolbox**Tasks hinzu:</span><span class="sxs-lookup"><span data-stu-id="46be2-194">To add tasks to the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="46be2-195">Klicken Sie im Menü **Extras** auf **Toolboxelemente auswählen**.</span><span class="sxs-lookup"><span data-stu-id="46be2-195">On the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
    2.  <span data-ttu-id="46be2-196">Wählen Sie die Tools aus, die in der **Toolbox**angezeigt werden sollen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="46be2-196">Select the tools you want to appear in the **Toolbox**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="46be2-197">Wenn Wartungsplantasks der **Toolbox** hinzugefügt werden, sind diese auch im **Wartungsplanungs-Assistenten**verfügbar.</span><span class="sxs-lookup"><span data-stu-id="46be2-197">Adding maintenance plan tasks to the **Toolbox** also makes them available in the **Maintenance Plan Wizard**.</span></span> <span data-ttu-id="46be2-198">Weitere Informationen zu den einzelnen Tasks finden Sie unter [Verwenden des Wartungsplanungs-Assistenten](use-the-maintenance-plan-wizard.md#SSMSProcedure) im Abschnitt **So starten Sie den Wartungsplanungs-Assistenten**.</span><span class="sxs-lookup"><span data-stu-id="46be2-198">For more information on the individual tasks above, see [Using Maintenance Plan Wizard](use-the-maintenance-plan-wizard.md#SSMSProcedure) under **Start the Maintenance Plan Wizard**.</span></span>  
  
8.  <span data-ttu-id="46be2-199">So definieren Sie einen Workflow zwischen Tasks:</span><span class="sxs-lookup"><span data-stu-id="46be2-199">To define a workflow between tasks:</span></span>  
  
    1.  <span data-ttu-id="46be2-200">Klicken Sie mit der rechten Maustaste auf den Vorgängertask, und wählen Sie **Rangfolgeneinschränkung hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="46be2-200">Right-click the precedent task and select **Add Precedence Constraint**.</span></span>  
  
    2.  <span data-ttu-id="46be2-201">Wählen Sie im Dialogfeld **Ablaufsteuerung** in der Liste **Zu** den abhängigen Task aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="46be2-201">In the **Control Flow** dialog box, in the **To** list, select the dependent task and click **OK**.</span></span>  
  
    3.  <span data-ttu-id="46be2-202">Doppelklicken Sie auf den Konnektor zwischen den beiden Tasks, um das Dialogfeld **Rangfolgeneinschränkungs-Editor** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="46be2-202">Double click the connector between the two tasks to open the **Precedence Constraint Editor** dialog box.</span></span>  
  
         <span data-ttu-id="46be2-203">Die folgenden Optionen sind im Dialogfeld **Rangfolgeneinschränkungs-Editor** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="46be2-203">The following options are available in the **Precedence Constraint Editor** dialog box.</span></span>  
  
         <span data-ttu-id="46be2-204">**Einschränkungsoption**</span><span class="sxs-lookup"><span data-stu-id="46be2-204">**Constraint option**</span></span>  
         <span data-ttu-id="46be2-205">Definiert, wie eine Einschränkung zwischen zwei Tasks angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="46be2-205">Defines how a constraint works between two tasks.</span></span>  
  
         <span data-ttu-id="46be2-206">Liste**Auswertungsvorgang**</span><span class="sxs-lookup"><span data-stu-id="46be2-206">**Evaluation operation**  list</span></span>  
         <span data-ttu-id="46be2-207">Geben Sie den Auswertungsvorgang an, den die Rangfolgeneinschränkung verwendet.</span><span class="sxs-lookup"><span data-stu-id="46be2-207">Specify the evaluation operation that the precedence constraint uses.</span></span> <span data-ttu-id="46be2-208">Folgende Vorgänge sind möglich: **Einschränkung**, **Ausdruck**, **Ausdruck und Einschränkung**und **Ausdruck oder Einschränkung**.</span><span class="sxs-lookup"><span data-stu-id="46be2-208">The operations are: **Constraint**, **Expression**, **Expression and Constraint**, and **Expression or Constraint**.</span></span>  
  
         <span data-ttu-id="46be2-209">Liste**Wert**</span><span class="sxs-lookup"><span data-stu-id="46be2-209">**Value** list</span></span>  
         <span data-ttu-id="46be2-210">Geben Sie den Einschränkungswert an: **Erfolg**, **Fehler**oder **Beendigung**.</span><span class="sxs-lookup"><span data-stu-id="46be2-210">Specify the constraint value: **Success**, **Failure**, or **Completion**.</span></span> <span data-ttu-id="46be2-211">**Erfolg** ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="46be2-211">**Success** is the default.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="46be2-212">Die Rangfolgeneinschränkungszeile wird für **Erfolg**grün, für **Fehler**rot und für **Beendigung**blau angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46be2-212">The precedence constraint line is green for **Success**, red for **Failure**, and blue for **Completion**.</span></span>  
  
         <span data-ttu-id="46be2-213">**Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="46be2-213">**Expression**</span></span>  
         <span data-ttu-id="46be2-214">Geben Sie, wenn Sie die Vorgänge **Ausdruck**, **Ausdruck und Einschränkung**oder **Ausdruck oder Einschränkung**verwenden, einen Ausdruck ein.</span><span class="sxs-lookup"><span data-stu-id="46be2-214">If using the operations **Expression**, **Expression and Constraint**, or **Expression or Constraint**, type an expression.</span></span> <span data-ttu-id="46be2-215">Der Ausdruck muss zu einem booleschen Wert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="46be2-215">The expression must evaluate to a Boolean.</span></span>  
  
         <span data-ttu-id="46be2-216">**Test**</span><span class="sxs-lookup"><span data-stu-id="46be2-216">**Test**</span></span>  
         <span data-ttu-id="46be2-217">Überprüfen Sie den Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="46be2-217">Validate the expression.</span></span>  
  
         <span data-ttu-id="46be2-218">**Mehrere Einschränkungen**</span><span class="sxs-lookup"><span data-stu-id="46be2-218">**Multiple constraints**</span></span>  
         <span data-ttu-id="46be2-219">Definieren Sie, wie mehrere Einschränkungen zusammenwirken, um die Ausführung des eingeschränkten Tasks zu steuern.</span><span class="sxs-lookup"><span data-stu-id="46be2-219">Define how multiple constraints interoperate to control the execution of the constrained task.</span></span>  
  
         <span data-ttu-id="46be2-220">**Logisches AND**</span><span class="sxs-lookup"><span data-stu-id="46be2-220">**Logical AND**</span></span>  
         <span data-ttu-id="46be2-221">Damit geben Sie an, dass für die ausführbare Datei mehrere Rangfolgeneinschränkungen gemeinsam überprüft werden müssen.</span><span class="sxs-lookup"><span data-stu-id="46be2-221">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="46be2-222">Sämtliche Einschränkungen müssen bei der Auswertung True ergeben.</span><span class="sxs-lookup"><span data-stu-id="46be2-222">All constraints must evaluate to True.</span></span> <span data-ttu-id="46be2-223">Diese Option ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="46be2-223">This option is the default.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="46be2-224">Dieser Typ der Rangfolgeneinschränkung wird als durchgehende grüne, rote oder blaue Linie dargestellt.</span><span class="sxs-lookup"><span data-stu-id="46be2-224">This type of precedence constraint appears as a solid green, red, or blue line.</span></span>  
  
         <span data-ttu-id="46be2-225">**Logisches OR**</span><span class="sxs-lookup"><span data-stu-id="46be2-225">**Logical OR**</span></span>  
         <span data-ttu-id="46be2-226">Damit geben Sie an, dass für die ausführbare Datei mehrere Rangfolgeneinschränkungen gemeinsam überprüft werden müssen.</span><span class="sxs-lookup"><span data-stu-id="46be2-226">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="46be2-227">Mindestens eine Einschränkung muss mit True ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="46be2-227">At least one constraint must evaluate to True.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="46be2-228">Dieser Typ der Rangfolgeneinschränkung wird als gestrichelte grüne, rote oder blaue Linie dargestellt.</span><span class="sxs-lookup"><span data-stu-id="46be2-228">This type of precedence constraint appears as a dotted green, red, or blue line.</span></span>  
  
9. <span data-ttu-id="46be2-229">Um einen anderen Unterplan mit Tasks hinzuzufügen, die unter einem anderen Zeitplan ausgeführt werden, klicken Sie in der Symbolleiste auf **Unterplan hinzufügen** , um das Dialogfeld **Unterplaneigenschaften** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="46be2-229">To add another subplan that contains tasks run on a different schedule, click **Add Subplan** on the toolbar to open the **Subplan Properties** dialog box.</span></span>  
  
10. <span data-ttu-id="46be2-230">So fügen Sie Verbindungen zu anderen Servern hinzu:</span><span class="sxs-lookup"><span data-stu-id="46be2-230">To add connections to different servers:</span></span>  
  
    1.  <span data-ttu-id="46be2-231">Klicken Sie in der Symbolleiste des Entwurfsbereichs auf **Verbindungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="46be2-231">In the design space's toolbar, click **Manage Connections**.</span></span>  
  
    2.  <span data-ttu-id="46be2-232">Klicken Sie im Dialogfeld **Verbindungen verwalten** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="46be2-232">In the **Manage Connections** dialog box, click **Add**.</span></span>  
  
    3.  <span data-ttu-id="46be2-233">Geben Sie im Dialogfeld **Verbindungseigenschaften** im Feld **Verbindungsname** den Namen der Verbindung ein, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="46be2-233">In the **Connection Properties** dialog box, in the **Connection name** box, enter the name of the connection you are creating.</span></span>  
  
    4.  <span data-ttu-id="46be2-234">Geben Sie unter **Geben Sie Folgendes für die Verbindung mit SQL Server-Daten an** im Feld **Wählen Sie einen Servernamen aus, oder geben Sie ihn ein** entweder den Namen des SQL-Servers ein, den Sie verwenden möchten, oder klicken Sie auf die Auslassungspunkte **(…)** , und wählen Sie im Dialogfeld **SQL Server** einen Server aus.</span><span class="sxs-lookup"><span data-stu-id="46be2-234">Under **Specify the following to connect to SQL Server data**, in the **Select or enter a server name** box, either enter the name of the SQL server you want to use or click the ellipsis **(...)** and select a server in the **SQL Server** dialog box.</span></span> <span data-ttu-id="46be2-235">Wenn Sie im Dialogfeld **SQL Server** einen Server auswählen, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="46be2-235">If you select a server from the **SQL Server** dialog box, click **OK**.</span></span>  
  
    5.  <span data-ttu-id="46be2-236">Wählen Sie unter **Geben Sie Informationen zum Anmelden am Server ein**die Option **Integrierte Sicherheit von Windows NT verwenden** oder **SQL Server-Authentifizierung verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="46be2-236">Under **Enter information to log on to the server**, select either **Use Windows NT Integrated security** or **Use a specific user name and password**.</span></span> <span data-ttu-id="46be2-237">Wenn Sie sich für die Verwendung der SQL Server-Authentifizierung entscheiden, geben Sie die entsprechenden Informationen in die Felder **Benutzername** und **Kennwort** ein.</span><span class="sxs-lookup"><span data-stu-id="46be2-237">If you elect to use a specific user name and password, enter that information in the **User name** and **Password** boxes, respectively.</span></span>  
  
    6.  <span data-ttu-id="46be2-238">Klicken Sie im Dialogfeld **Verbindungseigenschaften** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="46be2-238">In the **Connection Properties** dialog box, click **OK**.</span></span>  
  
    7.  <span data-ttu-id="46be2-239">Klicken Sie im Dialogfeld **Verbindungen verwalten** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="46be2-239">In the **Manage Connections** dialog box, click **Close**.</span></span>  
  
11. <span data-ttu-id="46be2-240">So geben Sie Berichtsoptionen an:</span><span class="sxs-lookup"><span data-stu-id="46be2-240">To specify reporting options:</span></span>  
  
    1.  <span data-ttu-id="46be2-241">Klicken Sie in der Symbolleiste des Entwurfsbereichs auf **Berichterstellung und Protokollierung**.</span><span class="sxs-lookup"><span data-stu-id="46be2-241">In the design space's toolbar, click **Reporting and Logging**.</span></span>  
  
    2.  <span data-ttu-id="46be2-242">Aktivieren Sie im Dialogfeld **Berichterstellung und Protokollierung** unter **Berichterstellung**die Option **Textdateibericht generieren** oder **Bericht an einen E-Mail-Empfänger senden** oder beide Optionen.</span><span class="sxs-lookup"><span data-stu-id="46be2-242">In the **Reporting and Logging** dialog box, under **Reporting**, select **Generate a text file report** or **Send report to an email recipient** or both.</span></span>  
  
        1.  <span data-ttu-id="46be2-243">Wenn Sie **Textdateibericht generieren**auswählen, können Sie entweder **Neue Datei erstellen** oder **An Datei anfügen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="46be2-243">If you select **Generate a text file report**, select either **Create a new file** or **Append to file**.</span></span>  
  
        2.  <span data-ttu-id="46be2-244">Geben Sie je nach Ihrer Auswahl den Namen und vollständigen Pfad der neuen Datei oder der anzufügenden Datei ein, indem Sie die Informationen im Feld **Ordner** bzw. **Dateiname** angeben.</span><span class="sxs-lookup"><span data-stu-id="46be2-244">Depending on the selection above, enter the name and full path of the new file or file to be appended by entering the information in the **Folder** or **File name** boxes.</span></span> <span data-ttu-id="46be2-245">Klicken Sie alternativ auf die Auslassungs Punkte **(...)** , und wählen Sie den Pfad zum Ordner oder Dateinamen aus den Dialogfeldern **Ordner suchen-**_server_name_ oder **Datenbankdateien suchen**_server_name_ aus.</span><span class="sxs-lookup"><span data-stu-id="46be2-245">Alternately, click on the ellipsis **(...)** and select the path to the folder or file name from the **Locate Folder -**_server_name_ or **Locate Database Files -**_server_name_ dialog boxes.</span></span>  
  
        3.  <span data-ttu-id="46be2-246">Wenn Sie in der Liste **Agentoperator**die Option **Bericht an einen E-Mail-Empfänger senden** auswählen, können Sie den Empfänger des per E-Mail gesendeten Berichts angeben.</span><span class="sxs-lookup"><span data-stu-id="46be2-246">If you select **Send report to an email recipient**, on the **Agent operator** list, select the recipient of the emailed report.</span></span>  
  
            > [!NOTE]  
            >  <span data-ttu-id="46be2-247">Der SQL Server-Agent muss für die Verwendung von Datenbank-E-Mail konfiguriert werden, um E-Mails senden zu können.</span><span class="sxs-lookup"><span data-stu-id="46be2-247">SQL Server Agent must be configured to use Database Mail in order to send mail.</span></span> <span data-ttu-id="46be2-248">Weitere Informationen finden Sie unter [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="46be2-248">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)</span></span>  
  
    3.  <span data-ttu-id="46be2-249">Wählen Sie zum Speichern detaillierter Informationen unter **Protokollierung**die Option **Erweiterte Informationen protokollieren**aus.</span><span class="sxs-lookup"><span data-stu-id="46be2-249">To save more detailed information, under **Logging**, select **Log extended information**.</span></span>  
  
    4.  <span data-ttu-id="46be2-250">Wählen Sie zum Schreiben von Informationen zu Wartungsplanergebnissen auf einen anderen Server die Option **Auf Remoteserver protokollieren** , und wählen Sie entweder eine Serververbindung aus der Liste **Verbindung** aus, oder klicken Sie auf **Neu** , und geben Sie die Verbindungsinformationen im Dialogfeld **Verbindungseigenschaften** ein.</span><span class="sxs-lookup"><span data-stu-id="46be2-250">To write maintenance plan results information to another server, select **Log to remote server** and either select a server connection from the **Connection** list or click **New** and enter the connection information in the **Connection Properties** dialog box.</span></span>  
  
    5.  <span data-ttu-id="46be2-251">Klicken Sie im Dialogfeld **Berichterstellung und Protokollierung** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="46be2-251">In the **Reporting and Logging** dialog box, click **OK**.</span></span>  
  
12. <span data-ttu-id="46be2-252">Wenn Sie die Ergebnisse im Protokolldatei-Viewer anzeigen möchten, klicken Sie im **Objekt-Explorer**mit der rechten Maustaste entweder auf den Ordner **Wartungspläne** oder auf einen bestimmten Wartungsplan, und klicken Sie dann auf **Verlauf anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="46be2-252">To view the results in the log file viewer, in **Object Explorer**, right-click either the **Maintenance Plans** folder or the specific maintenance plan and select **View History**.</span></span>  
  
     <span data-ttu-id="46be2-253">Die folgenden Optionen sind im Dialogfeld **Protokolldatei-Viewer-**_server_name_ verfügbar.</span><span class="sxs-lookup"><span data-stu-id="46be2-253">The following options are available on the **Log File Viewer -**_server_name_ dialog box.</span></span>  
  
     <span data-ttu-id="46be2-254">**Protokoll laden**</span><span class="sxs-lookup"><span data-stu-id="46be2-254">**Load Log**</span></span>  
     <span data-ttu-id="46be2-255">Öffnen Sie ein Dialogfeld, in dem Sie eine zu ladende Protokolldatei angeben können.</span><span class="sxs-lookup"><span data-stu-id="46be2-255">Open a dialog box where you can specify a log file to load.</span></span>  
  
     <span data-ttu-id="46be2-256">**Export**</span><span class="sxs-lookup"><span data-stu-id="46be2-256">**Export**</span></span>  
     <span data-ttu-id="46be2-257">Öffnen Sie ein Dialogfeld, in dem Sie die im Raster **Protokolldateizusammenfassung** angezeigten Informationen in eine Textdatei exportieren können.</span><span class="sxs-lookup"><span data-stu-id="46be2-257">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
     <span data-ttu-id="46be2-258">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="46be2-258">**Refresh**</span></span>  
     <span data-ttu-id="46be2-259">Aktualisieren Sie die Anzeige der ausgewählten Protokolle.</span><span class="sxs-lookup"><span data-stu-id="46be2-259">Refresh the view of the selected logs.</span></span> <span data-ttu-id="46be2-260">Beim Übernehmen von Filtereinstellungen werden mithilfe der Schaltfläche **Aktualisieren** die ausgewählten Protokolle erneut vom Zielserver gelesen.</span><span class="sxs-lookup"><span data-stu-id="46be2-260">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
     <span data-ttu-id="46be2-261">**Filter**</span><span class="sxs-lookup"><span data-stu-id="46be2-261">**Filter**</span></span>  
     <span data-ttu-id="46be2-262">Öffnen Sie ein Dialogfeld, in dem Sie zum Filtern der Protokolldatei verwendete Einstellungen angeben können, z.B. Filterkriterien wie **Verbindung**, **Datum**oder **Allgemein** .</span><span class="sxs-lookup"><span data-stu-id="46be2-262">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
     <span data-ttu-id="46be2-263">**Suchen,**</span><span class="sxs-lookup"><span data-stu-id="46be2-263">**Search**</span></span>  
     <span data-ttu-id="46be2-264">Durchsuchen Sie die Protokolldatei nach bestimmtem Text.</span><span class="sxs-lookup"><span data-stu-id="46be2-264">Search the log file for specific text.</span></span> <span data-ttu-id="46be2-265">Das Suchen mit Platzhalterzeichen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="46be2-265">Searching with wildcard characters is not supported.</span></span>  
  
     <span data-ttu-id="46be2-266">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="46be2-266">**Stop**</span></span>  
     <span data-ttu-id="46be2-267">Beendet das Laden der Protokolldateieinträge.</span><span class="sxs-lookup"><span data-stu-id="46be2-267">Stops loading the log file entries.</span></span> <span data-ttu-id="46be2-268">Diese Option können Sie z. B. verwenden, wenn das Laden einer Remote- oder Offline-Protokolldatei eine lange Zeit in Anspruch nimmt und Sie nur die zuletzt erstellten Einträge anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="46be2-268">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
     <span data-ttu-id="46be2-269">**Protokolldateizusammenfassung**</span><span class="sxs-lookup"><span data-stu-id="46be2-269">**Log file summary**</span></span>  
     <span data-ttu-id="46be2-270">In diesem Informationsbereich wird eine Zusammenfassung der Protokolldateifilterung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46be2-270">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="46be2-271">Wenn die Datei nicht gefiltert wurde, wird folgender Text angezeigt: **Kein Filter angewendet**.</span><span class="sxs-lookup"><span data-stu-id="46be2-271">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="46be2-272">Nach Anwendung eines Filters auf das Protokoll wird folgender Text angezeigt: **Filter log entries where:** \<filter criteria> (Protokolleinträge nach folgenden Kriterien filtern:).</span><span class="sxs-lookup"><span data-stu-id="46be2-272">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
     <span data-ttu-id="46be2-273">**Date**</span><span class="sxs-lookup"><span data-stu-id="46be2-273">**Date**</span></span>  
     <span data-ttu-id="46be2-274">Zeigt das Datum des Ereignisses an.</span><span class="sxs-lookup"><span data-stu-id="46be2-274">Displays the date of the event.</span></span>  
  
     <span data-ttu-id="46be2-275">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="46be2-275">**Source**</span></span>  
     <span data-ttu-id="46be2-276">Zeigt die Ausgangsfunktion an, mit dem das Ereignis erstellt wurde, z. B. den Namen des Diensts (z. B. MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="46be2-276">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="46be2-277">Dies wird nicht für alle Protokolltypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46be2-277">This does not appear for all log types.</span></span>  
  
     <span data-ttu-id="46be2-278">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="46be2-278">**Message**</span></span>  
     <span data-ttu-id="46be2-279">Zeigt die Meldungen an, die dem Ereignis zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="46be2-279">Displays any messages associated with the event.</span></span>  
  
     <span data-ttu-id="46be2-280">**Protokolltyp**</span><span class="sxs-lookup"><span data-stu-id="46be2-280">**Log Type**</span></span>  
     <span data-ttu-id="46be2-281">Zeigt den Typ des Protokolls an, zu dem das Ereignis gehört.</span><span class="sxs-lookup"><span data-stu-id="46be2-281">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="46be2-282">Alle ausgewählten Protokolle werden im Fenster für die Protokolldateizusammenfassung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46be2-282">All selected logs appear in the log file summary window.</span></span>  
  
     <span data-ttu-id="46be2-283">**Protokollquelle**</span><span class="sxs-lookup"><span data-stu-id="46be2-283">**Log Source**</span></span>  
     <span data-ttu-id="46be2-284">Zeigt eine Beschreibung des Quellprotokolls an, in dem das Ereignis aufgezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="46be2-284">Displays a description of the source log in which the event is captured.</span></span>  
  
     <span data-ttu-id="46be2-285">**Details für die ausgewählte Zeile**</span><span class="sxs-lookup"><span data-stu-id="46be2-285">**Selected row details**</span></span>  
     <span data-ttu-id="46be2-286">Wählen Sie eine Zahl aus, um am unteren Rand der Seite zusätzliche Details zu der ausgewählten Ereigniszeile anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="46be2-286">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="46be2-287">Die Spalten können durch Ziehen an neue Positionen im Raster neu angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="46be2-287">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="46be2-288">Die Breite der Spalten kann durch Ziehen der Spaltentrennbalken in der Kopfzeile des Rasters nach links oder rechts geändert werden.</span><span class="sxs-lookup"><span data-stu-id="46be2-288">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="46be2-289">Wenn Sie auf die Spaltentrennbalken in der Kopfzeile des Rasters doppelklicken, wird die Breite der Spalte automatisch an die Breite des Inhalts angepasst.</span><span class="sxs-lookup"><span data-stu-id="46be2-289">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
     <span data-ttu-id="46be2-290">**Instanz**</span><span class="sxs-lookup"><span data-stu-id="46be2-290">**Instance**</span></span>  
     <span data-ttu-id="46be2-291">Der Name der Instanz, bei der das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="46be2-291">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="46be2-292">Dieser wird im Format *Computername*\\*Instanzname*.</span><span class="sxs-lookup"><span data-stu-id="46be2-292">This is displayed as *computer name*\\*instance name*.</span></span>  
  
  
