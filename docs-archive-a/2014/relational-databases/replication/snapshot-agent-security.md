---
title: Sicherheit für den Momentaufnahme-Agent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.SSA.f1
helpviewer_keywords:
- Snapshot Agent Security dialog box
ms.assetid: 64e84c67-acc6-4906-98d4-3451767363fe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 288dc294b7ace9ea5cb098c8deec53c3ae4569a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622542"
---
# <a name="snapshot-agent-security"></a><span data-ttu-id="5f335-102">Sicherheit für den Momentaufnahme-Agent</span><span class="sxs-lookup"><span data-stu-id="5f335-102">Snapshot Agent Security</span></span>
  <span data-ttu-id="5f335-103">Mithilfe des Dialogfelds **Sicherheit für den Momentaufnahme-Agent** können Sie folgende Angaben machen:</span><span class="sxs-lookup"><span data-stu-id="5f335-103">The **Snapshot Agent Security** dialog box allows you to specify:</span></span>  
  
-   <span data-ttu-id="5f335-104">Das [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Konto, unter dem der Momentaufnahme-Agent auf dem Verteiler ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5f335-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Snapshot Agent runs at the Distributor.</span></span> <span data-ttu-id="5f335-105">Das Windows-Konto wird auch als *Prozesskonto*bezeichnet, da der Agentprozess unter diesem Konto ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5f335-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span>  
  
-   <span data-ttu-id="5f335-106">Kontext, unter dem der Momentaufnahmen-Agent Verbindungen mit dem [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Verleger herstellt</span><span class="sxs-lookup"><span data-stu-id="5f335-106">The context under which the Snapshot Agent makes connections to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher.</span></span> <span data-ttu-id="5f335-107">Die Verbindung kann entweder durch Identitätswechsel zum Windows-Konto oder unter dem Kontext eines von Ihnen angegebenen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Kontos hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5f335-107">The connection can be made by impersonating the Windows account or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f335-108">Der Momentaufnahme-Agent stellt Verbindungen mit dem Verleger her, auch wenn der Verleger und der Verteiler auf demselben Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5f335-108">The Snapshot Agent makes connections to the Publisher even if the Publisher and Distributor are on the same computer.</span></span> <span data-ttu-id="5f335-109">Der Momentaufnahme-Agent stellt auch Verbindungen mit dem Verteiler her. Diese Verbindungen werden immer durch einen Identitätswechsel zum Windows-Konto hergestellt, unter dem der Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5f335-109">The Snapshot Agent also makes connections to the Distributor; these connections are always made by impersonating the Windows account under which the agent runs.</span></span>  
  
     <span data-ttu-id="5f335-110">Geben Sie für Oracle-Verleger im Dialogfeld **Verlegereigenschaften** den Kontext an, unter dem der Momentaufnahme-Agent eine Verbindung mit dem Verleger herstellt (das Dialogfeld ist vom Dialogfeld **Verteilereigenschaften** aus verfügbar).</span><span class="sxs-lookup"><span data-stu-id="5f335-110">For Oracle Publishers, specify the context under which the Snapshot Agent connects to the Publisher in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="5f335-111">Weitere Informationen finden Sie unter [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="5f335-111">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="5f335-112">Alle Konten müssen gültig sein, und für jedes Konto muss das richtige Kennwort angegeben sein.</span><span class="sxs-lookup"><span data-stu-id="5f335-112">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="5f335-113">Konten und Kennwörter werden erst bei der Ausführung eines Agents überprüft.</span><span class="sxs-lookup"><span data-stu-id="5f335-113">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5f335-114">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5f335-114">Options</span></span>  
 <span data-ttu-id="5f335-115">**Prozesskonto**</span><span class="sxs-lookup"><span data-stu-id="5f335-115">**Process account**</span></span>  
 <span data-ttu-id="5f335-116">Geben Sie das Windows-Konto an, unter dem der Momentaufnahme-Agent auf dem Verteiler ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5f335-116">Enter a Windows account under which the Snapshot Agent runs at the Distributor.</span></span> <span data-ttu-id="5f335-117">Das angegebene Windows-Konto muss folgende Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="5f335-117">The Windows account you specify must:</span></span>  
  
-   <span data-ttu-id="5f335-118">Es muss mindestens Mitglied der festen Datenbankrolle **db_owner** in der Verteilungsdatenbank sein.</span><span class="sxs-lookup"><span data-stu-id="5f335-118">At minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
-   <span data-ttu-id="5f335-119">Es muss über Schreibberechtigungen für die Momentaufnahme-Freigabe verfügen.</span><span class="sxs-lookup"><span data-stu-id="5f335-119">Have write permissions on the snapshot share.</span></span>  
  
 <span data-ttu-id="5f335-120">**Kennwort** und **Kennwort bestätigen**</span><span class="sxs-lookup"><span data-stu-id="5f335-120">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="5f335-121">In diese Felder geben Sie das Kennwort für das Windows-Konto ein.</span><span class="sxs-lookup"><span data-stu-id="5f335-121">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="5f335-122">**Verbindung mit dem Verleger herstellen**</span><span class="sxs-lookup"><span data-stu-id="5f335-122">**Connect to the Publisher**</span></span>  
 <span data-ttu-id="5f335-123">Wählen Sie aus, ob der Momentaufnahme-Agent die Verbindungen mit dem Verleger entweder durch Annahme der Identität des im Textfeld **Prozesskonto** angegebenen Kontos oder mithilfe eines [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Kontos herstellen soll.</span><span class="sxs-lookup"><span data-stu-id="5f335-123">Select whether the Snapshot Agent should make connections to the Publisher by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="5f335-124">Wenn Sie sich für ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konto entscheiden, müssen Sie einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Benutzernamen und ein Kennwort eingeben.</span><span class="sxs-lookup"><span data-stu-id="5f335-124">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f335-125">Es wird empfohlen, kein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konto zu verwenden und stattdessen festzulegen, dass der Agent die Identität des Windows-Kontos annimmt.</span><span class="sxs-lookup"><span data-stu-id="5f335-125">It is recommended that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="5f335-126">Das für die Verbindung verwendete Windows-Konto bzw. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konto muss mindestens Mitglied der festen Datenbankrolle **db_owner** in der Veröffentlichungsdatenbank sein.</span><span class="sxs-lookup"><span data-stu-id="5f335-126">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must at minimum be a member of the **db_owner** fixed database role in the publication database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f335-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f335-127">See Also</span></span>  
 <span data-ttu-id="5f335-128">[Verwalten von Anmeldeinformationen und Kennwörtern bei der Replikation](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="5f335-128">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="5f335-129">[Sicherheitsmodell des Replikations-Agents](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="5f335-129">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="5f335-130">[Replikations-Agents (Übersicht)](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="5f335-130">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="5f335-131">Bewährte Methoden für die Replikationssicherheit</span><span class="sxs-lookup"><span data-stu-id="5f335-131">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
