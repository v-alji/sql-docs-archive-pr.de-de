---
title: Sicherheit für den Merge-Agent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.MA.f1
helpviewer_keywords:
- Merge Agent Security dialog box
ms.assetid: 9b86171a-4381-4b39-869a-cdc161e7cd15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ecbb044ca87ccfc74c5cb39a016667d15cf7a859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718058"
---
# <a name="merge-agent-security"></a><span data-ttu-id="b0e8f-102">Sicherheit für den Merge-Agent</span><span class="sxs-lookup"><span data-stu-id="b0e8f-102">Merge Agent Security</span></span>
  <span data-ttu-id="b0e8f-103">Im Dialogfeld **Sicherheit für den Merge-Agent** können Sie das [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Konto angeben, unter dem der Merge-Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-103">The **Merge Agent Security** dialog box allows you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Merge Agent runs.</span></span> <span data-ttu-id="b0e8f-104">Der Merge-Agent wird für Pushabonnements auf dem Verteiler und für Pullabonnements auf dem Abonnenten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-104">The Merge Agent runs at the Distributor for push subscriptions and at the Subscriber for pull subscriptions.</span></span> <span data-ttu-id="b0e8f-105">Das Windows-Konto wird auch als *Prozesskonto*bezeichnet, da der Agentprozess unter diesem Konto ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span> <span data-ttu-id="b0e8f-106">Abhängig davon, wie Sie auf dieses Dialogfeld zugreifen, stehen zusätzliche Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b0e8f-106">Additional options available in the dialog box depend on how you access it:</span></span>  
  
-   <span data-ttu-id="b0e8f-107">Wenn Sie das Dialogfeld über den Assistenten für neue Abonnements aufrufen, können Sie auch den Kontext angeben, unter dem der Merge-Agent Verbindungen mit dem Abonnenten (bei Pushabonnements) oder dem Verleger und Verteiler (bei Pullabonnements) herstellt.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-107">If the dialog box is accessed from the New Subscription Wizard, it also allows you to specify the context under which the Merge Agent makes connections to the Subscriber (for push subscriptions) or the Publisher and Distributor (for pull subscriptions).</span></span> <span data-ttu-id="b0e8f-108">Die Verbindung kann entweder mithilfe des Windows-Kontos oder unter dem Kontext eines von Ihnen angegebenen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Kontos hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-108">The connection can be made using the Windows account or under the context of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
-   <span data-ttu-id="b0e8f-109">Im Falle eines Zugriffs über das Dialogfeld **Abonnementeigenschaften** geben Sie den Kontext ein, unter dem der Merge-Agent Verbindungen herstellen soll, indem Sie in der Zeile**Abonnentenverbindung**bzw. **Verlegerverbindung** dieses Dialogfelds auf die **Schaltfläche mit den drei Punkten** klicken.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-109">If the dialog box is accessed from the **Subscription Properties** dialog box, specify the context under which the Merge Agent makes connections by clicking the properties button (**...**) in the **Subscriber Connection** or **Publisher Connection** row of that dialog box.</span></span> <span data-ttu-id="b0e8f-110">Weitere Informationen zum Zugreifen auf das Dialogfeld **Abonnementeigenschaften** finden Sie unter [Anzeigen und Ändern der Eigenschaften von Pushabonnements](view-and-modify-push-subscription-properties.md) und [Anzeigen und Ändern der Eigenschaften von Pullabonnements](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b0e8f-110">For more information about accessing the **Subscription Properties** dialog box, see [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) and how to: [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
 <span data-ttu-id="b0e8f-111">Alle Konten müssen gültig sein, und für jedes Konto muss das richtige Kennwort angegeben sein.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-111">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="b0e8f-112">Konten und Kennwörter werden erst bei der Ausführung eines Agents überprüft.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-112">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b0e8f-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b0e8f-113">Options</span></span>  
 <span data-ttu-id="b0e8f-114">**Process Account**</span><span class="sxs-lookup"><span data-stu-id="b0e8f-114">**Process Account**</span></span>  
 <span data-ttu-id="b0e8f-115">Geben Sie ein Windows-Konto ein, unter dem der Merge-Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-115">Enter a Windows account under which the Merge Agent runs.</span></span>  
  
-   <span data-ttu-id="b0e8f-116">Bei Pushabonnements muss das Konto folgende Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="b0e8f-116">For push subscriptions, the account must:</span></span>  
  
    -   <span data-ttu-id="b0e8f-117">Es muss mindestens Mitglied der festen Datenbankrolle **db_owner** in der Verteilungsdatenbank sein.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-117">At minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
    -   <span data-ttu-id="b0e8f-118">Es muss Mitglied der Veröffentlichungszugriffsliste sein.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-118">Be a member of the PAL.</span></span>  
  
    -   <span data-ttu-id="b0e8f-119">Die Anmeldung muss mit einem Benutzer in der Veröffentlichungsdatenbank verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-119">Be a login associated with a user in the publication database.</span></span>  
  
    -   <span data-ttu-id="b0e8f-120">Es muss über Leseberechtigungen für die Momentaufnahmefreigabe verfügen.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-120">Have read permissions on the snapshot share.</span></span>  
  
-   <span data-ttu-id="b0e8f-121">Bei Pullabonnements muss das Konto mindestens Mitglied der festen Datenbankrolle **db_owner** in der Abonnementdatenbank sein.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-121">For pull subscriptions, the account must at minimum be a member of the **db_owner** fixed database role in the subscription database.</span></span>  
  
 <span data-ttu-id="b0e8f-122">Zusätzliche Berechtigungen sind erforderlich, wenn beim Herstellen von Verbindungen die Identität des Prozesskontos angenommen wird.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-122">Additional permissions are required if the process account is impersonated when connections are made.</span></span> <span data-ttu-id="b0e8f-123">Siehe nachstehende Abschnitte **Verbindung mit dem Verleger und mit dem Verteiler herstellen** und **Verbindung mit dem Abonnenten herstellen** .</span><span class="sxs-lookup"><span data-stu-id="b0e8f-123">See the **Connect to the Publisher and Distributor** and **Connect to the Subscriber** sections below.</span></span>  
  
 <span data-ttu-id="b0e8f-124">Bei Pullabonnements für [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] kann kein **Prozesskonto** angegeben werden, da der Merge-Agent auf Instanzen von [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-124">**Process Account** cannot be specified for pull subscriptions to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], because the Merge Agent does not run on instances of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
 <span data-ttu-id="b0e8f-125">**Kennwort** und **Kennwort bestätigen**</span><span class="sxs-lookup"><span data-stu-id="b0e8f-125">**Password** and **Confirm Password**</span></span>  
 <span data-ttu-id="b0e8f-126">In diese Felder geben Sie das Kennwort für das Windows-Konto ein.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-126">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="b0e8f-127">**Verbindung mit dem Verleger und mit dem Verteiler herstellen**</span><span class="sxs-lookup"><span data-stu-id="b0e8f-127">**Connect to the Publisher and Distributor**</span></span>  
 <span data-ttu-id="b0e8f-128">Bei Pushabonnements werden Verbindungen mit dem Verleger und dem Verteiler immer hergestellt, indem der Agent die Identität des im Textfeld **Prozesskonto** angegebenen Kontos annimmt.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-128">For push subscriptions, connections to the Publisher and Distributor are always made by impersonating the account specified in the **Process account** text box.</span></span>  
  
 <span data-ttu-id="b0e8f-129">Bei Pullabonnements müssen Sie auswählen, ob der Merge-Agent die Verbindungen mit dem Verleger und dem Verteiler entweder durch Annahme der Identität des im Textfeld **Prozesskonto** angegebenen Kontos oder mithilfe eines [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Kontos herstellt.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-129">For pull subscriptions, select whether the Merge Agent should make connections to the Publisher and Distributor by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="b0e8f-130">Wenn Sie sich für ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konto entscheiden, müssen Sie einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Benutzernamen und ein Kennwort eingeben.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-130">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="b0e8f-131">empfiehlt, kein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konto zu verwenden und stattdessen festzulegen, dass der Agent die Identität des Windows-Kontos annimmt.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-131">recommends that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="b0e8f-132">Das für die Verbindung verwendete Windows-Konto bzw. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konto muss die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="b0e8f-132">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must:</span></span>  
  
-   <span data-ttu-id="b0e8f-133">Es muss Mitglied der Veröffentlichungszugriffsliste sein.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-133">Be a member of the PAL.</span></span>  
  
-   <span data-ttu-id="b0e8f-134">Die Anmeldung muss mit einem Benutzer in der Veröffentlichungsdatenbank verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-134">Be a login associated with a user in the publication database.</span></span>  
  
-   <span data-ttu-id="b0e8f-135">Die Anmeldung muss mit einem Benutzer in der Verteilungsdatenbank verknüpft sein (der Benutzer kann der Gastbenutzer sein).</span><span class="sxs-lookup"><span data-stu-id="b0e8f-135">Be a login associated with a user in the distribution database (the user can be the Guest user).</span></span>  
  
-   <span data-ttu-id="b0e8f-136">Es muss über Leseberechtigungen für die Momentaufnahmefreigabe verfügen.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-136">Have read permissions on the snapshot share.</span></span>  
  
 <span data-ttu-id="b0e8f-137">**Verbindung mit dem Abonnenten herstellen**</span><span class="sxs-lookup"><span data-stu-id="b0e8f-137">**Connect to the Subscriber**</span></span>  
 <span data-ttu-id="b0e8f-138">Bei Pullabonnements wird eine Verbindung mit dem Abonnenten immer hergestellt, indem die Identität des im Textfeld **Prozesskonto** angegebenen Kontos angenommen wird.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-138">For pull subscriptions, connections to the Subscriber are always made by impersonating the account specified in the **Process account** text box.</span></span>  
  
 <span data-ttu-id="b0e8f-139">Bei Pushabonnements müssen Sie auswählen, ob der Merge-Agent die Verbindungen mit dem Verleger und dem Verteiler entweder durch Annahme der Identität des im Textfeld **Prozesskonto** angegebenen Kontos oder mithilfe eines [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Kontos herstellt.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-139">For push subscriptions, select whether the Merge Agent should make connections to the Publisher and Distributor by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="b0e8f-140">Wenn Sie sich für ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konto entscheiden, müssen Sie einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Benutzernamen und ein Kennwort eingeben.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-140">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0e8f-141">Es wird empfohlen, kein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konto zu verwenden und stattdessen festzulegen, dass der Agent die Identität des Windows-Kontos annimmt.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-141">It is recommended that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="b0e8f-142">Das für die Verbindung mit dem Abonnenten verwendete Windows-Konto bzw. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konto muss mindestens Mitglied der festen Datenbankrolle **db_owner** in der Abonnementdatenbank sein.</span><span class="sxs-lookup"><span data-stu-id="b0e8f-142">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection to the Subscriber must at minimum be a member of the **db_owner** fixed database role in the subscription database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0e8f-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0e8f-143">See Also</span></span>  
 <span data-ttu-id="b0e8f-144">[Verwalten von Anmeldeinformationen und Kennwörtern bei der Replikation](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="b0e8f-144">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="b0e8f-145">[Sicherheitsmodell des Replikations-Agents](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="b0e8f-145">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="b0e8f-146">[Replikations-Agents (Übersicht)](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b0e8f-146">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 <span data-ttu-id="b0e8f-147">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="b0e8f-147">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="b0e8f-148">Abonnieren von Veröffentlichungen</span><span class="sxs-lookup"><span data-stu-id="b0e8f-148">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
