---
title: Dialogfeld 'Neue Richtlinie erstellen' oder 'Richtlinie öffnen', Seite 'Allgemein'|Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.newgroup.f1
- sql12.swb.dmf.policy.f1
- sql12.swb.dmf.policy.filter.f1
ms.assetid: c00bebd0-d04b-4c64-840e-8b7a2c603436
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4b67cb8faf18001b841824b806e7befc0683d457
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616018"
---
# <a name="create-new-policy-or-open-policy-dialog-box-general-page"></a><span data-ttu-id="e7c69-102">Dialogfeld 'Neue Richtlinie erstellen' oder 'Richtlinie öffnen', Seite 'Allgemein'</span><span class="sxs-lookup"><span data-stu-id="e7c69-102">Create New Policy or Open Policy Dialog Box, General Page</span></span>
  <span data-ttu-id="e7c69-103">Mithilfe dieses Dialogfelds können Sie eine neue richtlinienbasierte Verwaltungsrichtlinie erstellen oder eine vorhandene Richtlinie ändern.</span><span class="sxs-lookup"><span data-stu-id="e7c69-103">Use this dialog box to create a new Policy-Based Management policy or modify an existing policy.</span></span> <span data-ttu-id="e7c69-104">Verwenden Sie die Bereiche **Für Ziele** und **Serverbeschränkung** als Filter, um Richtlinien auf eine Teilmenge aller möglichen Ziele zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="e7c69-104">Use the **Against targets** and **Server restriction** areas as a filter to limit policies to a subset of all possible targets.</span></span> <span data-ttu-id="e7c69-105">Damit Bedingungen als Zielfilter verwendet werden können, müssen sie auf einem physischen Facet definiert werden und dürfen weder Funktionen noch den LIKE-Operator enthalten.</span><span class="sxs-lookup"><span data-stu-id="e7c69-105">For conditions to be used as target filters, they must be defined on a physical facet, must not contain functions, and must not contain the LIKE operator.</span></span> <span data-ttu-id="e7c69-106">Wenn das System den Objektsatz für eine Richtlinie berechnet, werden die Systemobjekte standardmäßig ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e7c69-106">When the system computes the object set for a policy, by default the system objects are excluded.</span></span>  <span data-ttu-id="e7c69-107">Falls der Objektsatz der Richtlinie z. B. auf alle Tabellen verweist, gilt die Richtlinie nicht für Systemtabellen.</span><span class="sxs-lookup"><span data-stu-id="e7c69-107">For example, if the object set of the policy refers to all tables, the policy will not apply to system tables.</span></span> <span data-ttu-id="e7c69-108">Wenn Benutzer eine Richtlinie in Verbindung mit Systemobjekten auswerten möchten, können sie dem Objektsatz Systemobjekte explizit hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e7c69-108">If users want to evaluate a policy against system objects, they can explicitly add system objects to the object set.</span></span> <span data-ttu-id="e7c69-109">Obwohl alle Richtlinien für den Auswertungsmodus **Zeitplan prüfen** unterstützt werden, werden aus Leistungsgründen jedoch nicht alle Richtlinien mit beliebigen Objektsätzen für den Auswertungsmodus **Änderungen prüfen** unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e7c69-109">However, though all policies are supported for **check on schedule** evaluation mode, for performance reason, not all policies with arbitrary object sets are supported for **check on change** evaluation mode.</span></span> <span data-ttu-id="e7c69-110">Weitere Informationen finden Sie unter [https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx](https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx).</span><span class="sxs-lookup"><span data-stu-id="e7c69-110">For more information, see [https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx](https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx)</span></span>  
  
## <a name="options"></a><span data-ttu-id="e7c69-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="e7c69-111">Options</span></span>  
 <span data-ttu-id="e7c69-112">**Name**</span><span class="sxs-lookup"><span data-stu-id="e7c69-112">**Name**</span></span>  
 <span data-ttu-id="e7c69-113">Geben Sie für eine neue Richtlinie den Namen der neuen Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="e7c69-113">For a new policy, type the new policy name.</span></span> <span data-ttu-id="e7c69-114">Für eine vorhandene Richtlinie wird der Name angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7c69-114">For an existing policy, the name is displayed.</span></span>  
  
 <span data-ttu-id="e7c69-115">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="e7c69-115">**Enabled**</span></span>  
 <span data-ttu-id="e7c69-116">Aktivieren Sie das Kontrollkästchen **Aktiviert** , um die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e7c69-116">Select the **Enabled** check box to enable the policy.</span></span> <span data-ttu-id="e7c69-117">Deaktivieren Sie das Kontrollkästchen **Aktiviert** , um die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e7c69-117">Clear the **Enabled** check box to disable the policy.</span></span> <span data-ttu-id="e7c69-118">Das Feld **Aktiviert** gilt für die Richtlinienautomatisierung.</span><span class="sxs-lookup"><span data-stu-id="e7c69-118">The **Enabled** box applies to policy automation.</span></span> <span data-ttu-id="e7c69-119">Es erstellt oder entfernt das Automatisierungssystem für die Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="e7c69-119">It creates or removes the automation system for the policy.</span></span> <span data-ttu-id="e7c69-120">Die Automatisierung verwendet die folgenden Mechanismen:</span><span class="sxs-lookup"><span data-stu-id="e7c69-120">Automation uses the following mechanisms:</span></span>  
  
 <span data-ttu-id="e7c69-121">**Bei Änderung - Verhindern**</span><span class="sxs-lookup"><span data-stu-id="e7c69-121">**On change: prevent**</span></span>  
 <span data-ttu-id="e7c69-122">Ein Datenbanktrigger erzwingt die Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="e7c69-122">A database trigger enforces compliance.</span></span>  
  
 <span data-ttu-id="e7c69-123">**Bei Änderung - Nur protokollieren**</span><span class="sxs-lookup"><span data-stu-id="e7c69-123">**On change: log only**</span></span>  
 <span data-ttu-id="e7c69-124">Ein Notification Services-Ereignis überprüft die Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="e7c69-124">A notification services event checks for compliance.</span></span>  
  
 <span data-ttu-id="e7c69-125">**Nach Zeitplan**</span><span class="sxs-lookup"><span data-stu-id="e7c69-125">**On schedule**</span></span>  
 <span data-ttu-id="e7c69-126">Ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Auftrag wird erstellt, um die Kompatibilität nach einem Zeitplan zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="e7c69-126">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job is created to check for compliance on a schedule.</span></span>  
  
 <span data-ttu-id="e7c69-127">Richtlinien, die unter Verwendung des Auswertungsmodus **Bedarfsgesteuert** ausgeführt werden, verwenden dieses Kontrollkästchen nicht.</span><span class="sxs-lookup"><span data-stu-id="e7c69-127">Policies that are run using **On demand** evaluation mode do not use this check box.</span></span>  
  
 <span data-ttu-id="e7c69-128">**Bedingung überprüfen**</span><span class="sxs-lookup"><span data-stu-id="e7c69-128">**Check condition**</span></span>  
 <span data-ttu-id="e7c69-129">Wählen Sie die richtlinienbasierte Verwaltungsbedingung aus, die diese Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="e7c69-129">Select the Policy-Based Management condition that this policy uses.</span></span> <span data-ttu-id="e7c69-130">Alle Bedingungen auf dem Server für das zugeordnete Facet der richtlinienbasierten Verwaltung werden aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="e7c69-130">All conditions on the server for the associated Policy-Based Management facet are listed.</span></span> <span data-ttu-id="e7c69-131">Klicken Sie auf **Neue Bedingung** , um eine neue Bedingung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e7c69-131">Click **New condition** to create a new condition.</span></span> <span data-ttu-id="e7c69-132">Klicken Sie auf die Schaltfläche mit den Auslassungspunkten ( **…** ), um die Bedingung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e7c69-132">Click the ellipsis (**...**) button to modify the condition.</span></span>  
  
 <span data-ttu-id="e7c69-133">**Für Ziele**</span><span class="sxs-lookup"><span data-stu-id="e7c69-133">**Against targets**</span></span>  
 <span data-ttu-id="e7c69-134">Wählen Sie die Zieltypen aus, die für dieses Facet verfügbar sind, um einen Filterausdruck abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e7c69-134">Select the target types that are available for this facet to complete a filter expression.</span></span>  
  
 <span data-ttu-id="e7c69-135">**Auswertungsmodus**</span><span class="sxs-lookup"><span data-stu-id="e7c69-135">**Evaluation Mode**</span></span>  
 <span data-ttu-id="e7c69-136">Wählen Sie den Auswertungsmodus für die Richtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="e7c69-136">Select the evaluation mode for the policy.</span></span> <span data-ttu-id="e7c69-137">Einige Richtlinien können überprüft werden, aber nicht erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="e7c69-137">Some policies can be checked but not enforced.</span></span> <span data-ttu-id="e7c69-138">Folgende Auswertungsmodi sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="e7c69-138">The evaluation modes are as follows:</span></span>  
  
 <span data-ttu-id="e7c69-139">**Bedarfsgesteuert**</span><span class="sxs-lookup"><span data-stu-id="e7c69-139">**On demand**</span></span>  
 <span data-ttu-id="e7c69-140">Die Richtlinie wird nur ausgeführt, wenn Sie sie über das Dialogfeld **Auswerten** ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7c69-140">Policy will only be run when you run it from the **Evaluate** dialog box.</span></span>  
  
 <span data-ttu-id="e7c69-141">**Nach Zeitplan**</span><span class="sxs-lookup"><span data-stu-id="e7c69-141">**On schedule**</span></span>  
 <span data-ttu-id="e7c69-142">Wertet die Richtlinie in regelmäßigen Abständen aus, zeichnet einen Protokolleintrag für Richtlinien auf, die Nicht-Einhaltungen aufweisen, und erstellt einen Bericht.</span><span class="sxs-lookup"><span data-stu-id="e7c69-142">Periodically evaluates the policy, records a log entry for policies that have out-of-compliance, and creates a report.</span></span> <span data-ttu-id="e7c69-143">Aktiviert das Feld **Zeitplan** .</span><span class="sxs-lookup"><span data-stu-id="e7c69-143">Enables the **Schedule** box.</span></span>  
  
 <span data-ttu-id="e7c69-144">**Bei Änderung - Nur protokollieren**</span><span class="sxs-lookup"><span data-stu-id="e7c69-144">**On change: log only**</span></span>  
 <span data-ttu-id="e7c69-145">Wenn versucht wird, Änderungen vorzunehmen, verhindert diese Option war keine nicht kompatiblen Änderungen, protokolliert jedoch Richtlinienverstöße.</span><span class="sxs-lookup"><span data-stu-id="e7c69-145">When changes are tried, this option does not prevent out-of-compliance changes, but logs policy violations.</span></span>  
  
 <span data-ttu-id="e7c69-146">**Bei Änderung - Verhindern**</span><span class="sxs-lookup"><span data-stu-id="e7c69-146">**On change: prevent**</span></span>  
 <span data-ttu-id="e7c69-147">Wenn versucht wird, Änderungen vorzunehmen, verhindert diese Option Änderungen, die gegen die Richtlinie verstoßen würden.</span><span class="sxs-lookup"><span data-stu-id="e7c69-147">When changes are tried, this option prevents changes that would violate the policy.</span></span>  
  
 <span data-ttu-id="e7c69-148">**Zeitplan**</span><span class="sxs-lookup"><span data-stu-id="e7c69-148">**Schedule**</span></span>  
 <span data-ttu-id="e7c69-149">Diese Option wird angezeigt, wenn der Auswertungsmodus **Nach Zeitplan** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="e7c69-149">This option appears when **On schedule** evaluation mode is selected.</span></span> <span data-ttu-id="e7c69-150">Geben Sie den Namen des Zeitplans ein, klicken Sie auf **Auswählen** , um einen Zeitplan aus der Liste auszuwählen, oder klicken Sie auf **Neu** , um einen neuen Zeitplan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e7c69-150">Type the name of the schedule, click **Pick** to select a schedule from a list, or click **New** to create a new schedule.</span></span> <span data-ttu-id="e7c69-151">Um den Zeitplanbereich zu aktivieren, muss **Nach Zeitplan** ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="e7c69-151">To enable the schedule area, **On schedule** must be selected.</span></span>  
  
 <span data-ttu-id="e7c69-152">**Serverbeschränkung**</span><span class="sxs-lookup"><span data-stu-id="e7c69-152">**Server restriction**</span></span>  
 <span data-ttu-id="e7c69-153">Wählen Sie die Typen von Servern aus, die für diese Richtlinie geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="e7c69-153">Select the types of servers that are appropriate for this policy.</span></span> <span data-ttu-id="e7c69-154">Optionen sind **Keine** , oder wählen Sie eine Bedingung aus, die die möglichen Server filtert.</span><span class="sxs-lookup"><span data-stu-id="e7c69-154">Options are **None** or select a condition that filters the possible servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7c69-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7c69-155">See Also</span></span>  
 [<span data-ttu-id="e7c69-156">Verwalten von Servern mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="e7c69-156">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
