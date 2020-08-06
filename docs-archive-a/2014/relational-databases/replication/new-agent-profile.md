---
title: Neues Agentprofil | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.newperfprofile.f1
helpviewer_keywords:
- New Agent Profile dialog box
ms.assetid: ebf59330-a421-45a5-9020-0484a96852bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1d7848e44585fd35a5b5a33cf431e15de96c9375
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721343"
---
# <a name="new-agent-profile"></a><span data-ttu-id="40eb5-102">Neues Agentprofil</span><span class="sxs-lookup"><span data-stu-id="40eb5-102">New Agent Profile</span></span>
  <span data-ttu-id="40eb5-103">Im Dialogfeld **Neues Agentprofil** können Sie ein neues Profil erstellen.</span><span class="sxs-lookup"><span data-stu-id="40eb5-103">Use the **New Agent Profile** dialog box to create a new profile.</span></span> <span data-ttu-id="40eb5-104">Neue Profile werden immer auf der Basis von vorhandenen Profilen erstellt. Sie können jedoch so geändert werden, dass bestimmte Anforderungen von Anwendungen erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="40eb5-104">New profiles are always based on existing profiles, but they can be modified to meet application requirements.</span></span> <span data-ttu-id="40eb5-105">Nach dem Erstellen kann das Profil auf vorhandene und zukünftige Agentaufträge im Dialogfeld **Agentprofile** angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="40eb5-105">After a profile has been created, it can be applied to existing and future agent jobs in the **Agent Profiles** dialog box.</span></span> <span data-ttu-id="40eb5-106">Agent-Parameterwerte können im Dialogfeld \<**AgentProfileName> – Eigenschaften\*\* geändert werden.</span><span class="sxs-lookup"><span data-stu-id="40eb5-106">Agent parameter values can be edited in the \<**AgentProfileName> Properties\*\* dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="40eb5-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="40eb5-107">Options</span></span>  
 <span data-ttu-id="40eb5-108">**Name**</span><span class="sxs-lookup"><span data-stu-id="40eb5-108">**Name**</span></span>  
 <span data-ttu-id="40eb5-109">Geben Sie einen Namen für das Profil ein.</span><span class="sxs-lookup"><span data-stu-id="40eb5-109">Enter a name for the profile.</span></span>  
  
 <span data-ttu-id="40eb5-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="40eb5-110">**Description**</span></span>  
 <span data-ttu-id="40eb5-111">Geben Sie eine Beschreibung für das Profil ein.</span><span class="sxs-lookup"><span data-stu-id="40eb5-111">Enter a description for the profile.</span></span>  
  
 <span data-ttu-id="40eb5-112">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="40eb5-112">**Parameter**</span></span>  
 <span data-ttu-id="40eb5-113">Die im Profil enthaltenen Agentparameter.</span><span class="sxs-lookup"><span data-stu-id="40eb5-113">The agent parameters included in the profile.</span></span> <span data-ttu-id="40eb5-114">In dem Profil, das als Basis für das neue Profil fungiert, müssen nicht notwendigerweise für alle Parameter Werte angegeben sein.</span><span class="sxs-lookup"><span data-stu-id="40eb5-114">The profile on which the new profile is based does not necessarily specify a value for each parameter.</span></span> <span data-ttu-id="40eb5-115">Wenn Sie alle für einen bestimmten Agent gültigen Parameter anzeigen möchten, müssen Sie das Kontrollkästchen **Nur die in diesem Profil verwendeten Parameter anzeigen** deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="40eb5-115">To see all parameters that are valid for a given agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="40eb5-116">Eine Beschreibung der einzelnen Parameter finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="40eb5-116">For descriptions of each parameter, see:</span></span>  
  
-   [<span data-ttu-id="40eb5-117">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="40eb5-117">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
-   [<span data-ttu-id="40eb5-118">Replikationsprotokolllese-Agent</span><span class="sxs-lookup"><span data-stu-id="40eb5-118">Replication Log Reader Agent</span></span>](agents/replication-log-reader-agent.md)  
  
-   [<span data-ttu-id="40eb5-119">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="40eb5-119">Replication Distribution Agent</span></span>](agents/replication-distribution-agent.md)  
  
-   [<span data-ttu-id="40eb5-120">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="40eb5-120">Replication Merge Agent</span></span>](agents/replication-merge-agent.md)  
  
-   [<span data-ttu-id="40eb5-121">Replication Queue Reader Agent</span><span class="sxs-lookup"><span data-stu-id="40eb5-121">Replication Queue Reader Agent</span></span>](agents/replication-queue-reader-agent.md)  
  
 <span data-ttu-id="40eb5-122">**Standardwert**</span><span class="sxs-lookup"><span data-stu-id="40eb5-122">**Default Value**</span></span>  
 <span data-ttu-id="40eb5-123">Der Standardwert für jeden Agentparameter.</span><span class="sxs-lookup"><span data-stu-id="40eb5-123">The default value for each agent parameter.</span></span>  
  
 <span data-ttu-id="40eb5-124">**Wert**</span><span class="sxs-lookup"><span data-stu-id="40eb5-124">**Value**</span></span>  
 <span data-ttu-id="40eb5-125">Der für den Parameter angegebene Wert in dem Profil, das als Basis für das neue Profil fungiert.</span><span class="sxs-lookup"><span data-stu-id="40eb5-125">The value specified for the parameter in the profile on which the new profile is based.</span></span> <span data-ttu-id="40eb5-126">Bearbeiten Sie dieses Feld für alle Parameterwerte, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="40eb5-126">Edit this field for any parameter values you want to change.</span></span>  
  
 <span data-ttu-id="40eb5-127">**Nur die in diesem Profil verwendeten Parameter anzeigen**</span><span class="sxs-lookup"><span data-stu-id="40eb5-127">**Show only parameters used in this profile**</span></span>  
 <span data-ttu-id="40eb5-128">Deaktivieren Sie das Kontrollkästchen, um nur die für einen bestimmten Agent gültigen Parameter anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="40eb5-128">Clear to show all valid parameters for a given agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40eb5-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40eb5-129">See Also</span></span>  
 <span data-ttu-id="40eb5-130">[Arbeiten mit Replikations-Agent-Profilen](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="40eb5-130">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="40eb5-131">[Replikations-Agents (Übersicht)](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="40eb5-131">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="40eb5-132">Replikations-Agent-Profile</span><span class="sxs-lookup"><span data-stu-id="40eb5-132">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
