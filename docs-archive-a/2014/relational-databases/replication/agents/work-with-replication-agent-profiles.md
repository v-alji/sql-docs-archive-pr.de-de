---
title: Arbeiten mit Replikations-Agent-Profilen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], agents and profiles
- replication agent profiles [SQL Server]
- agents [SQL Server replication], profiles
- profiles [SQL Server], replication agents
ms.assetid: 9c290a88-4e9f-4a7e-aab5-4442137a9918
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fc20451edfb1096fca7e468effb14df78b51f758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609145"
---
# <a name="work-with-replication-agent-profiles"></a><span data-ttu-id="28296-102">Arbeiten mit Replikations-Agent-Profilen</span><span class="sxs-lookup"><span data-stu-id="28296-102">Work with Replication Agent Profiles</span></span>
  <span data-ttu-id="28296-103">In diesem Thema wird beschrieben, wie in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder Replikationsverwaltungsobjekten (RMO) mit Replikations-Agentprofilen gearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="28296-103">This topic describes how to work with Replication Agent Profiles in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span> <span data-ttu-id="28296-104">Das Verhalten der einzelnen Replikations-Agents wird durch eine Reihe von Parametern gesteuert, die über Agentprofile festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="28296-104">The behavior of each replication agent is controlled by a set of parameters that can be set through agent profiles.</span></span> <span data-ttu-id="28296-105">Jeder Agent weist ein Standardprofil auf, und einige Agents besitzen weitere vordefinierte Profile, wobei für einen Agent jeweils immer nur ein Profil aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="28296-105">Each agent has a default profile, and some have additional predefined profiles; at a given time, only one profile is active for an agent.</span></span>  
  
 <span data-ttu-id="28296-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="28296-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="28296-107">**So arbeiten Sie mit Replikations-Agentprofilen mit:**</span><span class="sxs-lookup"><span data-stu-id="28296-107">**To work with Replication Agent Profiles, using:**</span></span>  
  
     [<span data-ttu-id="28296-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="28296-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
    -   <span data-ttu-id="28296-109">Auf das Dialogfeld Agentprofile zugreifen</span><span class="sxs-lookup"><span data-stu-id="28296-109">Access the Agent Profiles dialog box</span></span>  
  
    -   <span data-ttu-id="28296-110">Ein Profil für einen Agent angeben</span><span class="sxs-lookup"><span data-stu-id="28296-110">Specify a profile for an agent</span></span>  
  
    -   <span data-ttu-id="28296-111">Ein Profil erstellen</span><span class="sxs-lookup"><span data-stu-id="28296-111">Create a profile</span></span>  
  
    -   <span data-ttu-id="28296-112">Ein Profil ändern</span><span class="sxs-lookup"><span data-stu-id="28296-112">Modify a profile</span></span>  
  
    -   <span data-ttu-id="28296-113">Ein Profil löschen</span><span class="sxs-lookup"><span data-stu-id="28296-113">Delete a profile</span></span>  
  
     [<span data-ttu-id="28296-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="28296-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
    -   <span data-ttu-id="28296-115">Ein Profil erstellen</span><span class="sxs-lookup"><span data-stu-id="28296-115">Create a profile</span></span>  
  
    -   <span data-ttu-id="28296-116">Ein Profil ändern</span><span class="sxs-lookup"><span data-stu-id="28296-116">Modify a profile</span></span>  
  
    -   <span data-ttu-id="28296-117">Ein Profil löschen</span><span class="sxs-lookup"><span data-stu-id="28296-117">Delete a profile</span></span>  
  
    -   <span data-ttu-id="28296-118">Agentprofile während der Synchronisierung verwenden</span><span class="sxs-lookup"><span data-stu-id="28296-118">Use agent profiles during synchronization</span></span>  
  
    -   <span data-ttu-id="28296-119">Beispiel für Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="28296-119">Transact-SQL example</span></span>  
  
     [<span data-ttu-id="28296-120">Replikationsverwaltungsobjekte (RMO)</span><span class="sxs-lookup"><span data-stu-id="28296-120">Replication Management Objects</span></span>](#RMOProcedure)  
  
    -   <span data-ttu-id="28296-121">Ein Profil erstellen</span><span class="sxs-lookup"><span data-stu-id="28296-121">Create a profile</span></span>  
  
    -   <span data-ttu-id="28296-122">Ein Profil ändern</span><span class="sxs-lookup"><span data-stu-id="28296-122">Modify a profile</span></span>  
  
    -   <span data-ttu-id="28296-123">Ein Profil löschen</span><span class="sxs-lookup"><span data-stu-id="28296-123">Delete a profile</span></span>  
  
-   <span data-ttu-id="28296-124">**Nachverfolgung:**  [Nach dem Ändern der Agentparameter](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="28296-124">**Follow Up:**  [After Changing Agent Parameters](#FollowUp)</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="28296-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="28296-125">Using SQL Server Management Studio</span></span>  
  
###  <a name="to-access-the-agent-profiles-dialog-box-from-sql-server-management-studio"></a><a name="Access_SSMS"></a> <span data-ttu-id="28296-126">So greifen Sie auf das Dialogfeld Agentprofile in SQL Server Management Studio zu</span><span class="sxs-lookup"><span data-stu-id="28296-126">To access the Agent Profiles dialog box from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="28296-127">Klicken Sie im Dialogfeld **Verteilereigenschaften - \<Distributor>** auf der Seite **Allgemein** auf **Profilstandards**.</span><span class="sxs-lookup"><span data-stu-id="28296-127">On the **General** page of the **Distributor Properties - \<Distributor>** dialog box, click **Profile Defaults**.</span></span>  
  
#### <a name="to-access-the-agent-profiles-dialog-box-from-replication-monitor"></a><span data-ttu-id="28296-128">So greifen Sie über den Replikationsmonitor auf das Dialogfeld Agentprofile zu</span><span class="sxs-lookup"><span data-stu-id="28296-128">To access the Agent Profiles dialog box from Replication Monitor</span></span>  
  
-   <span data-ttu-id="28296-129">Um das Dialogfeld für alle Agents zu öffnen, klicken Sie mit der rechten Maustaste auf einen Verleger, und klicken Sie dann auf **Agentprofile**.</span><span class="sxs-lookup"><span data-stu-id="28296-129">To open the dialog box for all agents, right-click a Publisher, and then click **Agent Profiles**.</span></span>  
  
-   <span data-ttu-id="28296-130">Gehen Sie folgendermaßen vor, um das Dialogfeld für einen Agent zu öffnen:</span><span class="sxs-lookup"><span data-stu-id="28296-130">To open the dialog box for a single agent:</span></span>  
  
    1.  <span data-ttu-id="28296-131">Erweitern Sie im linken Bereich des Replikationsmonitors eine Verlegergruppe, erweitern Sie einen Verleger, und klicken Sie dann auf eine Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="28296-131">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
    2.  <span data-ttu-id="28296-132">Klicken Sie bei Verteilungs-Agent- oder Merge-Agent-Profilen auf der Registerkarte **Alle Abonnements** mit der rechten Maustaste auf ein Abonnement, und klicken Sie dann auf **Agentprofil**.</span><span class="sxs-lookup"><span data-stu-id="28296-132">For Distribution Agent and Merge Agent profiles, right-click a subscription on the **All Subscriptions** tab, and then click **Agent Profile**.</span></span> <span data-ttu-id="28296-133">Klicken Sie bei anderen Agents auf der Registerkarte **Agents** mit der rechten Maustaste auf den Agent, und klicken Sie dann auf **Agentprofil**.</span><span class="sxs-lookup"><span data-stu-id="28296-133">For other agents, right-click the agent on the **Agents** tab, and then click **Agent Profile**.</span></span>  
  
###  <a name="to-specify-a-profile-for-an-agent"></a><a name="Specify_SSMS"></a> <span data-ttu-id="28296-134">So geben Sie ein Profil für einen Agent an</span><span class="sxs-lookup"><span data-stu-id="28296-134">To specify a profile for an agent</span></span>  
  
1.  <span data-ttu-id="28296-135">Wenn im Dialogfeld **Agentprofile** Profile für mehrere Agents angezeigt werden, wählen Sie einen Agent aus.</span><span class="sxs-lookup"><span data-stu-id="28296-135">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="28296-136">Wählen Sie im Raster **Agentprofile** in der **Default for new** -Spalte ein Profil aus.</span><span class="sxs-lookup"><span data-stu-id="28296-136">Select a profile in the **Default for new** column of the **Agent profiles** grid.</span></span> <span data-ttu-id="28296-137">Standardmäßig wird das Profil nur auf Agents für neue Veröffentlichungen und Abonnements angewendet.</span><span class="sxs-lookup"><span data-stu-id="28296-137">By default, the profile is only applied to agents for new publications and subscriptions.</span></span>  
  
3.  <span data-ttu-id="28296-138">Wenn Sie angeben möchten, dass dieses Profil von allen Agents des ausgewählten Typs für vorhandene Veröffentlichungen oder Abonnements verwendet werden soll, klicken Sie auf **Vorhandene Agents ändern**.</span><span class="sxs-lookup"><span data-stu-id="28296-138">To specify that all agents of the selected type for existing publications or subscriptions should use this profile, click **Change existing agents**.</span></span>  
  
###  <a name="to-view-and-edit-the-parameters-associated-with-a-profile"></a><a name="Modify_SSMS"></a> <span data-ttu-id="28296-139">So zeigen Sie einem Profil zugeordnete Parameter an und bearbeiten Sie die Parameter</span><span class="sxs-lookup"><span data-stu-id="28296-139">To view and edit the parameters associated with a profile</span></span>  
  
1.  <span data-ttu-id="28296-140">Wenn im Dialogfeld **Agentprofile** Profile für mehrere Agents angezeigt werden, wählen Sie einen Agent aus.</span><span class="sxs-lookup"><span data-stu-id="28296-140">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="28296-141">Klicken Sie auf die Eigenschaftenschaltfläche ( **…** ) neben einem Profil.</span><span class="sxs-lookup"><span data-stu-id="28296-141">Click the properties button (**...**) next to a profile.</span></span>  
  
3.  <span data-ttu-id="28296-142">Im Dialogfeld **\<ProfileName>-Profileigenschaften** werden die Parameter und Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28296-142">View the parameters and values in the **\<ProfileName> Profile Properties** dialog box.</span></span>  
  
    -   <span data-ttu-id="28296-143">Parameter in benutzerdefinierten Profilen können bearbeitet werden; Parameter in vordefinierten Systemprofilen können nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="28296-143">Parameters in user-defined profiles can be edited; parameters in predefined system profiles cannot.</span></span>  
  
    -   <span data-ttu-id="28296-144">Um alle Parameter für einen Agent anzuzeigen, deaktivieren Sie das Kontrollkästchen **Nur die in diesem Profil verwendeten Parameter anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="28296-144">To view all parameters for an agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="28296-145">Informationen zu den Agentparametern finden Sie unter den Links am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="28296-145">For information about agent parameters, see the links at the end of this topic.</span></span>  
  
4.  <span data-ttu-id="28296-146">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="28296-146">Click **Close**.</span></span>  
  
###  <a name="to-create-a-user-defined-profile"></a><a name="Create_SSMS"></a> <span data-ttu-id="28296-147">So erstellen Sie ein benutzerdefiniertes Profil</span><span class="sxs-lookup"><span data-stu-id="28296-147">To create a user-defined profile</span></span>  
  
1.  <span data-ttu-id="28296-148">Wenn im Dialogfeld **Agentprofile** Profile für mehrere Agents angezeigt werden, wählen Sie einen Agent aus.</span><span class="sxs-lookup"><span data-stu-id="28296-148">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="28296-149">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="28296-149">Click **New**.</span></span>  
  
3.  <span data-ttu-id="28296-150">Wählen Sie im Initialisierungsdialogfeld **Neues Agentprofil** ein vorhandenes Profil aus, auf dem das neue Profil basieren soll.</span><span class="sxs-lookup"><span data-stu-id="28296-150">In the **New Agent Profile** initialization dialog box, select an existing profile on which to base the new profile.</span></span>  
  
4.  <span data-ttu-id="28296-151">Geben Sie im Dialogfeld **Neues Agentprofil** Werte in die Textfelder **Name** und **Beschreibung** ein.</span><span class="sxs-lookup"><span data-stu-id="28296-151">In the **New Agent Profile** dialog box, enter values in the **Name** and **Description** text boxes.</span></span>  
  
5.  <span data-ttu-id="28296-152">Ändern Sie die Parameter in dem gewünschten Profil entsprechend.</span><span class="sxs-lookup"><span data-stu-id="28296-152">Modify parameters to tailor the profile.</span></span> <span data-ttu-id="28296-153">Um alle Parameter für einen Agent anzuzeigen, deaktivieren Sie das Kontrollkästchen **Nur die in diesem Profil verwendeten Parameter anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="28296-153">To view all parameters for an agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="28296-154">Informationen zu den Agentparametern finden Sie unter den Links am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="28296-154">For information about agent parameters, see the links at the end of this topic.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
###  <a name="to-delete-a-user-defined-profile"></a><a name="Delete_SSMS"></a> <span data-ttu-id="28296-155">So löschen Sie ein benutzerdefiniertes Profil</span><span class="sxs-lookup"><span data-stu-id="28296-155">To delete a user-defined profile</span></span>  
  
1.  <span data-ttu-id="28296-156">Wenn im Dialogfeld **Agentprofile** Profile für mehrere Agents angezeigt werden, wählen Sie einen Agent aus.</span><span class="sxs-lookup"><span data-stu-id="28296-156">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="28296-157">Wenn ein Profil einem oder mehreren Agents zugeordnet ist, ändern Sie das Profil für diese Agents:</span><span class="sxs-lookup"><span data-stu-id="28296-157">If a profile is associated with one or more agents, change the profile for those agents:</span></span>  
  
    1.  <span data-ttu-id="28296-158">Wählen Sie im Raster **Agentprofile** ein anderes Profil aus.</span><span class="sxs-lookup"><span data-stu-id="28296-158">Select a different profile in the **Agent profiles** grid.</span></span>  
  
    2.  <span data-ttu-id="28296-159">Klicken Sie auf **Vorhandene Agents ändern**.</span><span class="sxs-lookup"><span data-stu-id="28296-159">Click **Change existing agents**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="28296-160">Dadurch wird das Profil nicht nur für die Agents geändert, deren Profil Sie löschen möchten, sondern für alle Agents des ausgewählten Typs für vorhandene Veröffentlichungen oder Abonnements.</span><span class="sxs-lookup"><span data-stu-id="28296-160">This will change the profile for all agents of the selected type for existing publications or subscriptions, not only the ones using the profile you want to delete.</span></span>  
  
3.  <span data-ttu-id="28296-161">Wählen Sie das zu löschende Profil aus, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="28296-161">Select the profile you want to delete, and then click **Delete**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="28296-162">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="28296-162">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-new-agent-profile"></a><a name="Create_tsql"></a> <span data-ttu-id="28296-163">So erstellen Sie ein neues Agentprofil</span><span class="sxs-lookup"><span data-stu-id="28296-163">To create a new agent profile</span></span>  
  
1.  <span data-ttu-id="28296-164">Führen Sie auf dem Verteiler [sp_add_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-profile-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="28296-164">At the Distributor, execute [sp_add_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-profile-transact-sql).</span></span> <span data-ttu-id="28296-165">Geben Sie **@name** , den Wert **1** für **@profile_type** und einen der folgenden Werte für an **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="28296-165">Specify **@name**, a value of **1** for **@profile_type**, and one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="28296-166">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-166">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-167">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-167">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-168">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-168">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-169">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-169">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-170">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-170">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="28296-171">Wenn dieses Profil zum neuen Standardprofil für den zugehörigen Typ von Replikations-Agent wird, geben Sie einen Wert **1** für **@default**.</span><span class="sxs-lookup"><span data-stu-id="28296-171">If this profile will become the new default profile for its type of replication agent, specify a value of **1** for **@default**.</span></span> <span data-ttu-id="28296-172">Der Bezeichner für das neue Profil wird mithilfe des **@profile_id** Output-Parameters zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="28296-172">The identifier for the new profile is returned using the **@profile_id** output parameter.</span></span> <span data-ttu-id="28296-173">Dadurch wird ein neues Profil mit einem Satz von Profilparametern erstellt, das auf dem Standardprofil des bestimmten Agenttyps basiert.</span><span class="sxs-lookup"><span data-stu-id="28296-173">This creates a new profile with a set of profile parameters based on the default profile for the given agent type.</span></span>  
  
2.  <span data-ttu-id="28296-174">Nach der Erstellung des neuen Profils können Sie Standardparameter hinzufügen, entfernen oder ändern, um das Profil anzupassen.</span><span class="sxs-lookup"><span data-stu-id="28296-174">After the new profile has been created, add, remove, or modify the default parameters to customize the profile.</span></span>  
  
###  <a name="to-modify-an-existing-agent-profile"></a><a name="Modify_tsql"></a> <span data-ttu-id="28296-175">So ändern Sie ein vorhandenes Agentprofil</span><span class="sxs-lookup"><span data-stu-id="28296-175">To modify an existing agent profile</span></span>  
  
1.  <span data-ttu-id="28296-176">Führen Sie auf dem Verteiler [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="28296-176">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="28296-177">Geben Sie einen der folgenden Werte für an **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="28296-177">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="28296-178">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-178">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-179">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-179">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-180">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-180">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-181">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-181">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-182">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-182">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="28296-183">Dadurch werden alle Profile für den angegebenen Agenttyp zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="28296-183">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="28296-184">Beachten Sie den Wert **profile_id** im Resultset für das zu ändernde Profil.</span><span class="sxs-lookup"><span data-stu-id="28296-184">Note the value of **profile_id** in the result set for the profile to change.</span></span>  
  
2.  <span data-ttu-id="28296-185">Führen Sie auf dem Verteiler [sp_help_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-parameter-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="28296-185">At the Distributor, execute [sp_help_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-parameter-transact-sql).</span></span> <span data-ttu-id="28296-186">Geben Sie den Bezeichner des Profils aus Schritt 1 für an **@profile_id** .</span><span class="sxs-lookup"><span data-stu-id="28296-186">Specify the profile identifier from step 1 for **@profile_id**.</span></span> <span data-ttu-id="28296-187">Dadurch werden alle Parameter für das Profil zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="28296-187">This returns all parameters for the profile.</span></span> <span data-ttu-id="28296-188">Beachten Sie den Namen der zu ändernden Parameter bzw. der aus dem Profil zu entfernenden Parameter.</span><span class="sxs-lookup"><span data-stu-id="28296-188">Note the name of any parameters to modify or remove from the profile.</span></span>  
  
3.  <span data-ttu-id="28296-189">Führen Sie [sp_change_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-agent-profile-transact-sql) aus, um den Wert eines Parameters in einem Profil zu ändern.</span><span class="sxs-lookup"><span data-stu-id="28296-189">To change the value of a parameter in a profile, execute [sp_change_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-agent-profile-transact-sql).</span></span> <span data-ttu-id="28296-190">Geben Sie den Bezeichner des Profils aus Schritt 1 für **@profile_id** , den Namen des Parameters, der geändert **@property** werden soll, und einen neuen Wert für den Parameter für an **@value** .</span><span class="sxs-lookup"><span data-stu-id="28296-190">Specify the profile identifier from step 1 for **@profile_id**, the name of the parameter to change for **@property**, and a new value for the parameter for **@value**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="28296-191">Es ist nicht möglich, ein vorhandenes Agentprofil in das Standardprofil für einen Agent zu ändern.</span><span class="sxs-lookup"><span data-stu-id="28296-191">You cannot change an existing agent profile to become the default profile for an agent.</span></span> <span data-ttu-id="28296-192">Stattdessen müssen Sie ein neues Profil als Standardprofil erstellen, wie in der vorherigen Prozedur beschrieben.</span><span class="sxs-lookup"><span data-stu-id="28296-192">You must instead create a new profile as the default profile, as shown in the previous procedure.</span></span>  
  
4.  <span data-ttu-id="28296-193">Führen [sp_drop_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-parameter-transact-sql) aus, um einen Parameter von einem Profil zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="28296-193">To remove a parameter from a profile, execute [sp_drop_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-parameter-transact-sql).</span></span> <span data-ttu-id="28296-194">Geben Sie den Bezeichner des Profils aus Schritt 1 für **@profile_id** und den Namen des Parameters an, der entfernt werden soll **@parameter_name** .</span><span class="sxs-lookup"><span data-stu-id="28296-194">Specify the profile identifier from step 1 for **@profile_id** and the name of the parameter to remove for **@parameter_name**.</span></span>  
  
5.  <span data-ttu-id="28296-195">Sie müssen die folgenden Schritte ausführen, um einem Profil einen neuen Parameter hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="28296-195">To add a new parameter to a profile, you must do the following:</span></span>  
  
    -   <span data-ttu-id="28296-196">Fragen Sie die Tabelle [MSagentparameterlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/msagentparameterlist-transact-sql) auf dem Verteiler ab, um die Profilparameter zu bestimmen, die für die einzelnen Agenttypen festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="28296-196">Query the [MSagentparameterlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/msagentparameterlist-transact-sql) table at the Distributor to determine which profile parameters can be set for each agent type.</span></span>  
  
    -   <span data-ttu-id="28296-197">Führen Sie auf dem Verteiler [sp_add_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-parameter-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="28296-197">At the Distributor, execute [sp_add_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-parameter-transact-sql).</span></span> <span data-ttu-id="28296-198">Geben Sie den Bezeichner des Profils aus Schritt 1 für **@profile_id** , den Namen eines gültigen Parameters, der hinzugefügt **@parameter_name** werden soll, und den Wert des Parameters für an **@parameter_value** .</span><span class="sxs-lookup"><span data-stu-id="28296-198">Specify the profile identifier from step 1 for **@profile_id**, the name of a valid parameter to add for **@parameter_name**, and the value of the parameter for **@parameter_value**.</span></span>  
  
###  <a name="to-delete-an-agent-profile"></a><a name="Delete_tsql"></a> <span data-ttu-id="28296-199">So löschen Sie ein Agentprofil</span><span class="sxs-lookup"><span data-stu-id="28296-199">To delete an agent profile</span></span>  
  
1.  <span data-ttu-id="28296-200">Führen Sie auf dem Verteiler [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="28296-200">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="28296-201">Geben Sie einen der folgenden Werte für an **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="28296-201">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="28296-202">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-202">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-203">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-203">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-204">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-204">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-205">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-205">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-206">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-206">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="28296-207">Dadurch werden alle Profile für den angegebenen Agenttyp zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="28296-207">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="28296-208">Beachten Sie den Wert **profile_id** im Resultset für das zu entfernende Profil.</span><span class="sxs-lookup"><span data-stu-id="28296-208">Note the value of **profile_id** in the result set for the profile to remove.</span></span>  
  
2.  <span data-ttu-id="28296-209">Führen Sie auf dem Verteiler [sp_drop_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-profile-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="28296-209">At the Distributor, execute [sp_drop_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-profile-transact-sql).</span></span> <span data-ttu-id="28296-210">Geben Sie den Bezeichner des Profils aus Schritt 1 für an **@profile_id** .</span><span class="sxs-lookup"><span data-stu-id="28296-210">Specify the profile identifier from step 1 for **@profile_id**.</span></span>  
  
###  <a name="to-use-agent-profiles-during-synchronization"></a><a name="Synch_tsql"></a> <span data-ttu-id="28296-211">So verwenden Sie während der Synchronisierung Agentprofile</span><span class="sxs-lookup"><span data-stu-id="28296-211">To use agent profiles during synchronization</span></span>  
  
1.  <span data-ttu-id="28296-212">Führen Sie auf dem Verteiler [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="28296-212">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="28296-213">Geben Sie einen der folgenden Werte für an **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="28296-213">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="28296-214">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-214">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-215">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-215">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-216">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-216">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-217">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-217">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="28296-218">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="28296-218">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="28296-219">Dadurch werden alle Profile für den angegebenen Agenttyp zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="28296-219">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="28296-220">Notieren Sie den Wert `profile_name` im Resultset für das zu verwendende Profil.</span><span class="sxs-lookup"><span data-stu-id="28296-220">Note the value of `profile_name` in the result set for the profile to use.</span></span>  
  
2.  <span data-ttu-id="28296-221">Wenn der Agent von einem Agentauftrag aus gestartet wird, bearbeiten Sie den Auftrags Schritt, mit dem der Agent gestartet wird, um den Wert von zu bestimmen, der `profile_name` in Schritt 1 nach dem-Profile Name **-** Befehlszeilenparameter abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="28296-221">If the agent is started from an agent job, edit the job step that starts the agent to specify the value of `profile_name` obtained in step 1 after the **-ProfileName** command-line parameter.</span></span> <span data-ttu-id="28296-222">Weitere Informationen finden Sie unter [Anzeigen und Ändern von Befehlszeilenparametern des Replikations-Agents &#40;SQL Server Management Studio&#41;](view-and-modify-replication-agent-command-prompt-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="28296-222">For more information, see [View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;](view-and-modify-replication-agent-command-prompt-parameters.md).</span></span>  
  
3.  <span data-ttu-id="28296-223">Wenn Sie den-Agent von der Eingabeaufforderung aus starten, geben Sie den Wert von an, der `profile_name` in Schritt 1 nach dem-Profile Name **-** Befehlszeilenparameter abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="28296-223">When starting the agent from the command prompt, specify the value of `profile_name` obtained in step 1 after the **-ProfileName** command-line parameter.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="28296-224">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="28296-224">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="28296-225">In diesem Beispiel werden ein benutzerdefiniertes Profil für den Merge-Agent mit der Bezeichnung **custom_merge**erstellt, der Wert des **-UploadReadChangesPerBatch** -Parameters geändert, ein neuer **-ExchangeType** -Parameter hinzugefügt und Informationen zu dem Profil, das erstellt wird, zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="28296-225">This example creates a custom profile for the Merge Agent named **custom_merge**, changes the value of the **-UploadReadChangesPerBatch** parameter, adds a new **-ExchangeType** parameter, and returns information on the profile that is created.</span></span>  
  
 [!code-sql[HowTo#sp_addagentprofileparam](../../../snippets/tsql/SQL15/replication/howto/tsql/createperfparammerge.sql#sp_addagentprofileparam)]  
  
##  <a name="using-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="28296-226">Verwenden von RMO</span><span class="sxs-lookup"><span data-stu-id="28296-226">Using RMO</span></span>  
  
###  <a name="to-create-a-new-agent-profile"></a><a name="Create_RMO"></a> <span data-ttu-id="28296-227">So erstellen Sie ein neues Agentprofil</span><span class="sxs-lookup"><span data-stu-id="28296-227">To create a new agent profile</span></span>  
  
1.  <span data-ttu-id="28296-228">Erstellen Sie eine Verbindung mit dem Verteiler, indem Sie eine Instanz der <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="28296-228">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="28296-229">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.AgentProfile>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="28296-229">Create an instance of the <xref:Microsoft.SqlServer.Replication.AgentProfile> class.</span></span>  
  
3.  <span data-ttu-id="28296-230">Legen Sie die folgenden Eigenschaften für das Objekt fest:</span><span class="sxs-lookup"><span data-stu-id="28296-230">Set the following properties on the object:</span></span>  
  
    -   <span data-ttu-id="28296-231"><xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> - der Name des Profils.</span><span class="sxs-lookup"><span data-stu-id="28296-231"><xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> - the name for the profile.</span></span>  
  
    -   <span data-ttu-id="28296-232"><xref:Microsoft.SqlServer.Replication.AgentProfile.AgentType%2A> - ein <xref:Microsoft.SqlServer.Replication.AgentType> -Wert, der den Typ des Replikations-Agents angibt, für den das Profil erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="28296-232"><xref:Microsoft.SqlServer.Replication.AgentProfile.AgentType%2A> - an <xref:Microsoft.SqlServer.Replication.AgentType> value that specifies the type of replication agent for which the profile is being created.</span></span>  
  
    -   <span data-ttu-id="28296-233"><xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> - die in Schritt 1 erstellte <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="28296-233"><xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> - the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> created in step 1.</span></span>  
  
    -   <span data-ttu-id="28296-234">(Optional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Description%2A> - eine Beschreibung des Profils.</span><span class="sxs-lookup"><span data-stu-id="28296-234">(Optional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Description%2A> - a description of the profile.</span></span>  
  
    -   <span data-ttu-id="28296-235">(Optional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Default%2A> - Legen Sie diese Eigenschaft auf `true` fest, wenn alle neuen Agentaufträge für diesen <xref:Microsoft.SqlServer.Replication.AgentType> dieses Profil standardmäßig verwenden.</span><span class="sxs-lookup"><span data-stu-id="28296-235">(Optional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Default%2A> - set this property to `true` if all new agent jobs for this <xref:Microsoft.SqlServer.Replication.AgentType> will use this profile by default.</span></span>  
  
4.  <span data-ttu-id="28296-236">Rufen Sie die <xref:Microsoft.SqlServer.Replication.AgentProfile.Create%2A> -Methode auf, um das Profil auf dem Server zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="28296-236">Call the <xref:Microsoft.SqlServer.Replication.AgentProfile.Create%2A> method to create the profile on the server.</span></span>  
  
5.  <span data-ttu-id="28296-237">Sobald das Profil auf dem Server vorhanden ist, können Sie es anpassen, indem Sie Werte für die Parameter für Replikations-Agents hinzufügen, entfernen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="28296-237">Once the profile exists on the server, you can customize it by adding, removing, or changing the values of replication agent parameters.</span></span>  
  
6.  <span data-ttu-id="28296-238">Rufen Sie die <xref:Microsoft.SqlServer.Replication.AgentProfile.AssignToAgent%2A> -Methode auf, um das Profil einem vorhandenen Auftrag des Replikations-Agents zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="28296-238">To assign the profile to an existing replication agent job, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.AssignToAgent%2A> method.</span></span> <span data-ttu-id="28296-239">Übergeben Sie den Namen der Verteilungsdatenbank für *distributionDBName* und die ID des Auftrags für *agentID*.</span><span class="sxs-lookup"><span data-stu-id="28296-239">Pass the name of the distribution database for *distributionDBName* and the ID of the job for *agentID*.</span></span>  
  
###  <a name="to-modify-an-existing-agent-profile"></a><a name="Modify_RMO"></a> <span data-ttu-id="28296-240">So ändern Sie ein vorhandenes Agentprofil</span><span class="sxs-lookup"><span data-stu-id="28296-240">To modify an existing agent profile</span></span>  
  
1.  <span data-ttu-id="28296-241">Erstellen Sie eine Verbindung mit dem Verteiler, indem Sie eine Instanz der <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="28296-241">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="28296-242">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.ReplicationServer>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="28296-242">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="28296-243">Übergeben Sie das in Schritt 1 erstellte <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Objekt.</span><span class="sxs-lookup"><span data-stu-id="28296-243">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object created in step 1.</span></span>  
  
3.  <span data-ttu-id="28296-244">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="28296-244">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="28296-245">Überprüfen Sie, ob der Verteiler vorhanden ist, wenn diese Methode `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="28296-245">If this method returns `false`, verify that the Distributor exists.</span></span>  
  
4.  <span data-ttu-id="28296-246">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationServer.EnumAgentProfiles%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="28296-246">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.EnumAgentProfiles%2A> method.</span></span> <span data-ttu-id="28296-247">Übergeben Sie einen <xref:Microsoft.SqlServer.Replication.AgentType> -Wert, um die zurückgegebenen Profile für einen bestimmten Typ von Replikations-Agent einzugrenzen.</span><span class="sxs-lookup"><span data-stu-id="28296-247">Pass an <xref:Microsoft.SqlServer.Replication.AgentType> value to narrow down the returned profiles to a specific type of replication agent.</span></span>  
  
5.  <span data-ttu-id="28296-248">Rufen Sie das gewünschte <xref:Microsoft.SqlServer.Replication.AgentProfile> -Objekt von der zurückgegebenen <xref:System.Collections.ArrayList>ab, wobei die <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> -Eigenschaft des Objekt mit dem Profilnamen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="28296-248">Get the desired <xref:Microsoft.SqlServer.Replication.AgentProfile> object from the returned <xref:System.Collections.ArrayList>, where the <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> property of the object matches the profile name.</span></span>  
  
6.  <span data-ttu-id="28296-249">Rufen Sie eine der folgenden Methoden von <xref:Microsoft.SqlServer.Replication.AgentProfile> auf, um das Profil zu ändern:</span><span class="sxs-lookup"><span data-stu-id="28296-249">Call one of the following methods of <xref:Microsoft.SqlServer.Replication.AgentProfile> to change the profile:</span></span>  
  
    -   <span data-ttu-id="28296-250"><xref:Microsoft.SqlServer.Replication.AgentProfile.AddParameter%2A> - fügt dem Profil einen unterstützten Parameter hinzu, wobei *name* der Name des Parameters für den Replikations-Agent und *value* der angegebene Wert ist.</span><span class="sxs-lookup"><span data-stu-id="28296-250"><xref:Microsoft.SqlServer.Replication.AgentProfile.AddParameter%2A> - adds a supported parameter to the profile, where *name* is the name of the replication agent parameter and *value* is the specified value.</span></span> <span data-ttu-id="28296-251">Rufen Sie zum Aufzählen aller unterstützten Agentparameter für einen bestimmten Agenttyp die <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="28296-251">To enumerate all supported agent parameters for a given agent type, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> method.</span></span> <span data-ttu-id="28296-252">Diese Methode gibt eine <xref:System.Collections.ArrayList> von <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> -Objekten zurück, die alle unterstützten Parameter darstellen.</span><span class="sxs-lookup"><span data-stu-id="28296-252">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> objects that represent all supported parameters.</span></span>  
  
    -   <span data-ttu-id="28296-253"><xref:Microsoft.SqlServer.Replication.AgentProfile.RemoveParameter%2A> - entfernt einen vorhandenen Parameter aus dem Profil, wobei *name* der Name des Parameters für den Replikations-Agent ist.</span><span class="sxs-lookup"><span data-stu-id="28296-253"><xref:Microsoft.SqlServer.Replication.AgentProfile.RemoveParameter%2A> - removes an existing parameter from the profile, where *name* is the name of the replication agent parameter.</span></span> <span data-ttu-id="28296-254">Rufen Sie zum Aufzählen aller aktuellen Agentparameter, die für das Profil definiert sind, die <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="28296-254">To enumerate all current agent parameters defined for the profile, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> method.</span></span> <span data-ttu-id="28296-255">Diese Methode gibt eine <xref:System.Collections.ArrayList> von <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> -Objekten zurück, die den vorhandenen Parameter für dieses Profil darstellen.</span><span class="sxs-lookup"><span data-stu-id="28296-255">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> objects that represent the existing parameter for this profile.</span></span>  
  
    -   <span data-ttu-id="28296-256"><xref:Microsoft.SqlServer.Replication.AgentProfile.ChangeParameter%2A> - ändert die Einstellung eines vorhandenen Parameters im Profil, wobei *name* der Name des Agentparameters und *newValue* der Wert ist, in den der Parameter geändert wird.</span><span class="sxs-lookup"><span data-stu-id="28296-256"><xref:Microsoft.SqlServer.Replication.AgentProfile.ChangeParameter%2A> - changes the setting of an existing parameter in the profile, where *name* is the name of the agent parameter and *newValue* is the value to which the parameter is being changed.</span></span> <span data-ttu-id="28296-257">Rufen Sie zum Aufzählen aller aktuellen Agentparameter, die für das Profil definiert sind, die <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="28296-257">To enumerate all current agent parameters defined for the profile, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> method.</span></span> <span data-ttu-id="28296-258">Diese Methode gibt eine <xref:System.Collections.ArrayList> von <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> -Objekten zurück, die den vorhandenen Parameter für dieses Profil darstellen.</span><span class="sxs-lookup"><span data-stu-id="28296-258">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> objects that represent the existing parameter for this profile.</span></span> <span data-ttu-id="28296-259">Rufen Sie zum Aufzählen aller unterstützten Einstellungen für den Agentparameter die <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="28296-259">To enumerate all supported agent parameter settings, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> method.</span></span> <span data-ttu-id="28296-260">Diese Methode gibt eine <xref:System.Collections.ArrayList> von <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> -Objekten zurück, die die unterstützten Werte für alle Parameter darstellen.</span><span class="sxs-lookup"><span data-stu-id="28296-260">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> objects that represent the supported values for all parameters.</span></span>  
  
###  <a name="to-delete-an-agent-profile"></a><a name="Delete_RMO"></a> <span data-ttu-id="28296-261">So löschen Sie ein Agentprofil</span><span class="sxs-lookup"><span data-stu-id="28296-261">To delete an agent profile</span></span>  
  
1.  <span data-ttu-id="28296-262">Erstellen Sie eine Verbindung mit dem Verteiler, indem Sie eine Instanz der <xref:Microsoft.SqlServer.Management.Common.ServerConnection> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="28296-262">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="28296-263">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.Replication.AgentProfile>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="28296-263">Create an instance of the <xref:Microsoft.SqlServer.Replication.AgentProfile> class.</span></span> <span data-ttu-id="28296-264">Legen Sie den Namen des Profils für <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> und <xref:Microsoft.SqlServer.Management.Common.ServerConnection> aus Schritt 1 für <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>fest.</span><span class="sxs-lookup"><span data-stu-id="28296-264">Set the name of the profile for <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> and the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="28296-265">Rufen Sie die <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="28296-265">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="28296-266">Wenn diese Methode `false` zurückgibt, wurde ein falscher Name angegeben, oder das Profil ist auf dem Server nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="28296-266">If this method returns `false`, either the specified name was incorrect or the profile does not exist on the server.</span></span>  
  
4.  <span data-ttu-id="28296-267">Stellen Sie sicher, dass die <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A> -Eigenschaft auf <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.User>festgelegt ist, womit ein Kundenprofil angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="28296-267">Verify that the <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A> property is set to <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.User>, which indicates a customer profile.</span></span> <span data-ttu-id="28296-268">Entfernen Sie kein Profil, das einen Wert <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.System> für <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A>aufweist.</span><span class="sxs-lookup"><span data-stu-id="28296-268">You should not remove a profile that has a value of <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.System> for <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A>.</span></span>  
  
5.  <span data-ttu-id="28296-269">Rufen Sie die <xref:Microsoft.SqlServer.Replication.AgentProfile.Remove%2A> -Methode auf, um das benutzerdefinierte Profil, das durch dieses Objekt dargestellt wird, vom Server zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="28296-269">Call the <xref:Microsoft.SqlServer.Replication.AgentProfile.Remove%2A> method to remove the user-defined profile represented by this object from the server.</span></span>  
  
##  <a name="follow-up-after-changing-agent-parameters"></a><a name="FollowUp"></a><span data-ttu-id="28296-270">Nächster Schritt: Nach dem Ändern der Agentparameter</span><span class="sxs-lookup"><span data-stu-id="28296-270">Follow Up: After Changing Agent Parameters</span></span>  
 <span data-ttu-id="28296-271">Die Änderungen der Agentparameter treten in Kraft, wenn der Agent das nächste Mal gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="28296-271">Agent parameter changes take effect the next time the agent is started.</span></span> <span data-ttu-id="28296-272">Wenn der Agent ständig ausgeführt wird, müssen Sie den Agent beenden und neu starten.</span><span class="sxs-lookup"><span data-stu-id="28296-272">If the agent runs continuously, you must stop and restart the agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28296-273">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28296-273">See Also</span></span>  
 <span data-ttu-id="28296-274">[Replikations-Agent-Profile](replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="28296-274">[Replication Agent Profiles](replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="28296-275">[Replication Snapshot Agent](replication-snapshot-agent.md) </span><span class="sxs-lookup"><span data-stu-id="28296-275">[Replication Snapshot Agent](replication-snapshot-agent.md) </span></span>  
 <span data-ttu-id="28296-276">[Replication Log Reader Agent](replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="28296-276">[Replication Log Reader Agent](replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="28296-277">[Replication Distribution Agent](replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="28296-277">[Replication Distribution Agent](replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="28296-278">[Replication Merge Agent](replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="28296-278">[Replication Merge Agent](replication-merge-agent.md) </span></span>  
 [<span data-ttu-id="28296-279">Replication Queue Reader Agent</span><span class="sxs-lookup"><span data-stu-id="28296-279">Replication Queue Reader Agent</span></span>](replication-queue-reader-agent.md)  
  
  
