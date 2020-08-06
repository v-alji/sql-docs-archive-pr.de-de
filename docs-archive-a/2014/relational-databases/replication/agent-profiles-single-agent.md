---
title: Agentprofile (einzelner Agent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.perfprofileagentname.f1
helpviewer_keywords:
- Agent Profile dialog box
ms.assetid: 22713555-c496-4ce1-8ec7-4ae75cfadca8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7def9a6fef4e7e66076ee18552705c6071dab134
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615961"
---
# <a name="agent-profiles-single-agent"></a><span data-ttu-id="fc6f0-102">Agentprofile (einzelner Agent)</span><span class="sxs-lookup"><span data-stu-id="fc6f0-102">Agent Profiles (single agent)</span></span>
  <span data-ttu-id="fc6f0-103">Mithilfe des Dialogfelds **Agentprofile** können Sie Agentprofile verwalten.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-103">Use the **Agent Profiles** dialog box to manage profiles for an agent.</span></span> <span data-ttu-id="fc6f0-104">Agentprofile stellen eine einfache Möglichkeit dar, die Laufzeitparameter jedes Agents zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-104">Agent profiles provide a convenient way to manage the runtime parameters for each agent.</span></span> <span data-ttu-id="fc6f0-105">Jeder Agent verfügt über ein Standardprofil, und einige Agents verfügen über zusätzliche vordefinierte Profile.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-105">Each agent has a default profile, and some agents have additional predefined profiles.</span></span> <span data-ttu-id="fc6f0-106">Der Merge-Agent verfügt z. B. über ein Profil für langsame Verbindungen, das für Verbindungen mit geringer Bandbreite angelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-106">For example, the Merge Agent has a "slow link" profile designed for low bandwidth connections.</span></span> <span data-ttu-id="fc6f0-107">Die vordefinierten Profile reichen für die meisten Anwendungen aus, aber Sie können auch benutzerdefinierte Profile erstellen, mit denen Sie das Verhalten der Agents je nach Bedarf anpassen können.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-107">Predefined profiles are sufficient for most applications, but you can also create user-defined profiles, allowing you to customize agent behavior.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fc6f0-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="fc6f0-108">Options</span></span>  
 <span data-ttu-id="fc6f0-109">**Standardwert für Neu**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-109">**Default for New**</span></span>  
 <span data-ttu-id="fc6f0-110">Wählen Sie das Profil aus, das verwendet werden soll, wenn für einen Agent des angegebenen Typs Aufträge erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-110">Select the profile that will be used when jobs are created for an agent of a given type.</span></span> <span data-ttu-id="fc6f0-111">Wenn Sie z. B. mehrere Abonnements für eine Mergeveröffentlichung erstellen, wird für den Auftrag des Merge-Agents für jedes Abonnement das ausgewählte Profil verwendet.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-111">For example, if you create a number of subscriptions to a merge publication, the Merge Agent job for each subscription will use the profile selected.</span></span> <span data-ttu-id="fc6f0-112">Wenn Sie das Profil für vorhandene Aufträge ändern möchten, wählen Sie ein Profil aus, und klicken Sie auf **Vorhandene Agents ändern**.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-112">If you want to change the profile for existing jobs, select a profile, and then click **Change Existing Agents**.</span></span>  
  
 <span data-ttu-id="fc6f0-113">**Name**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-113">**Name**</span></span>  
 <span data-ttu-id="fc6f0-114">Der Name des Profils.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-114">The name of the profile.</span></span>  
  
 <span data-ttu-id="fc6f0-115">**Typ**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-115">**Type**</span></span>  
 <span data-ttu-id="fc6f0-116">Der Typ des Profils: **Benutzer** (benutzerdefiniert) oder **System** (vordefiniert).</span><span class="sxs-lookup"><span data-stu-id="fc6f0-116">The type of profile: **User** (user-defined) or **System** (predefined).</span></span>  
  
 <span data-ttu-id="fc6f0-117">**Eigenschaften (...)**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-117">**Properties (...)**</span></span>  
 <span data-ttu-id="fc6f0-118">Klicken Sie auf diese Option, um die Werte anzuzeigen, die für jeden Parameter im Agentprofil verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-118">Click to view the values used for each parameter in the agent profile.</span></span>  
  
 <span data-ttu-id="fc6f0-119">**Neu**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-119">**New**</span></span>  
 <span data-ttu-id="fc6f0-120">Klicken Sie hier, um ein neues Profil zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-120">Click to create a new profile.</span></span>  
  
 <span data-ttu-id="fc6f0-121">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-121">**Delete**</span></span>  
 <span data-ttu-id="fc6f0-122">Wählen Sie ein benutzerdefiniertes Profil aus, und klicken Sie auf **Löschen** , um dieses Profil zu löschen.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-122">Select a user-defined profile, and then click **Delete** to delete that profile.</span></span> <span data-ttu-id="fc6f0-123">Vordefinierte Profile können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-123">Predefined profiles cannot be deleted.</span></span>  
  
 <span data-ttu-id="fc6f0-124">**Vorhandene Agents ändern**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-124">**Change Existing Agents**</span></span>  
 <span data-ttu-id="fc6f0-125">Wählen Sie ein Profil aus, und klicken Sie dann auf **Vorhandene Agents ändern** , um anzugeben, dass alle vorhandenen Aufträge für einen Agent des angegebenen Typs das ausgewählte Profil verwenden sollen.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-125">Select a profile, and then click **Change Existing Agents** to specify that all existing jobs for an agent of a given type should use the selected profile.</span></span> <span data-ttu-id="fc6f0-126">Wenn Sie z. B. mehrere Abonnements für eine Mergeveröffentlichung erstellt haben und das Profil so ändern möchten, dass die Merge-Agentaufträge für alle diese Abonnements das **Agentprofil für langsame Links**verwenden, wählen Sie dieses Profil aus, und klicken Sie auf **Vorhandene Agents ändern**.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-126">For example, if you have created a number of subscriptions to a merge publication, and you want to change the profile to specify that the Merge Agent job for each of these subscriptions should use the **Slow link agent profile**, select that profile, and then click **Change Existing Agents**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc6f0-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc6f0-127">See Also</span></span>  
 <span data-ttu-id="fc6f0-128">[Arbeiten mit Replikations-Agent-Profilen](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="fc6f0-128">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="fc6f0-129">[Replikations-Agents (Übersicht)](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="fc6f0-129">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="fc6f0-130">Replikations-Agent-Profile</span><span class="sxs-lookup"><span data-stu-id="fc6f0-130">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
