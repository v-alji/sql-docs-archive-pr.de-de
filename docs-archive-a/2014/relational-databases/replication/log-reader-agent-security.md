---
title: Sicherheit für den Protokolllese-Agent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.LRA.f1
helpviewer_keywords:
- Log Reader Agent Security dialog box
ms.assetid: d6981e74-ddb8-41b8-9ea1-56c2ece63b8a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4be41aa9135e20a334616b9cb9d76a773f8d0e9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723690"
---
# <a name="log-reader-agent-security"></a><span data-ttu-id="ef773-102">Sicherheit für den Protokolllese-Agent</span><span class="sxs-lookup"><span data-stu-id="ef773-102">Log Reader Agent Security</span></span>
  <span data-ttu-id="ef773-103">Mithilfe des Dialogfelds **Sicherheit für den Protokolllese-Agent** können Sie folgende Angaben machen:</span><span class="sxs-lookup"><span data-stu-id="ef773-103">The **Log Reader Agent Security** dialog box allows you to specify:</span></span>  
  
-   <span data-ttu-id="ef773-104">Das [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Konto, unter dem der Protokolllese-Agent auf dem Verteiler ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ef773-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Log Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="ef773-105">Das Windows-Konto wird auch als *Prozesskonto*bezeichnet, da der Agentprozess unter diesem Konto ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ef773-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span>  
  
-   <span data-ttu-id="ef773-106">Der Kontext, unter dem der Protokolllese-Agent Verbindungen mit dem [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Herausgeber herstellt.</span><span class="sxs-lookup"><span data-stu-id="ef773-106">The context under which the Log Reader Agent makes connections to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher.</span></span> <span data-ttu-id="ef773-107">Die Verbindung kann entweder durch Identitätswechsel zum Windows-Konto oder unter dem Kontext eines von Ihnen angegebenen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Kontos hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ef773-107">The connection can be made by impersonating the Windows account or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ef773-108">Der Protokolllese-Agent stellt Verbindungen mit dem Verleger her, auch wenn der Verleger und der Verteiler auf demselben Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ef773-108">The Log Reader Agent makes connections to the Publisher even if the Publisher and Distributor are on the same computer.</span></span> <span data-ttu-id="ef773-109">Der Protokolllese-Agent stellt auch Verbindungen mit dem Verteiler her. Diese Verbindungen werden immer durch einen Identitätswechsel zum Windows-Konto hergestellt, unter dem der Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ef773-109">The Log Reader Agent also makes connections to the Distributor; these connections are always made by impersonating the Windows account under which the agent runs.</span></span>  
  
     <span data-ttu-id="ef773-110">Geben Sie für Oracle-Verleger im Dialogfeld **Verlegereigenschaften** den Kontext an, unter dem der Protokolllese-Agent eine Verbindung mit dem Verleger herstellt (das Dialogfeld ist vom Dialogfeld **Verteilereigenschaften** aus verfügbar).</span><span class="sxs-lookup"><span data-stu-id="ef773-110">For Oracle Publishers, specify the context under which the Log Reader Agent connects to the Publisher in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="ef773-111">Weitere Informationen finden Sie unter [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ef773-111">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="ef773-112">Alle Konten müssen gültig sein, und für jedes Konto muss das richtige Kennwort angegeben sein.</span><span class="sxs-lookup"><span data-stu-id="ef773-112">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="ef773-113">Konten und Kennwörter werden erst bei der Ausführung eines Agents überprüft.</span><span class="sxs-lookup"><span data-stu-id="ef773-113">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ef773-114">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ef773-114">Options</span></span>  
 <span data-ttu-id="ef773-115">**Prozesskonto**</span><span class="sxs-lookup"><span data-stu-id="ef773-115">**Process account**</span></span>  
 <span data-ttu-id="ef773-116">Geben Sie das Windows-Konto an, unter dem der Protokolllese-Agent auf dem Verteiler ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ef773-116">Enter a Windows account under which the Log Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="ef773-117">Das angegebene Windows-Konto muss mindestens ein Mitglied der festen Datenbankrolle **db_owner** in der Verteilungsdatenbank sein.</span><span class="sxs-lookup"><span data-stu-id="ef773-117">The Windows account you specify must at minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
 <span data-ttu-id="ef773-118">**Kennwort** und **Kennwort bestätigen**</span><span class="sxs-lookup"><span data-stu-id="ef773-118">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="ef773-119">In diese Felder geben Sie das Kennwort für das Windows-Konto ein.</span><span class="sxs-lookup"><span data-stu-id="ef773-119">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="ef773-120">**Verbindung mit dem Verleger herstellen**</span><span class="sxs-lookup"><span data-stu-id="ef773-120">**Connect to the Publisher**</span></span>  
 <span data-ttu-id="ef773-121">Wählen Sie aus, ob der Protokolllese-Agent die Verbindungen mit dem Verleger entweder durch Annahme der Identität des im Textfeld **Prozesskonto** angegebenen Kontos oder mithilfe eines [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Kontos herstellen soll.</span><span class="sxs-lookup"><span data-stu-id="ef773-121">Select whether the Log Reader Agent should make connections to the Publisher by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="ef773-122">Wenn Sie sich für ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konto entscheiden, müssen Sie einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Benutzernamen und ein Kennwort eingeben.</span><span class="sxs-lookup"><span data-stu-id="ef773-122">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="ef773-123">empfiehlt, kein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konto zu verwenden und stattdessen festzulegen, dass der Agent die Identität des Windows-Kontos annimmt.</span><span class="sxs-lookup"><span data-stu-id="ef773-123">recommends that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="ef773-124">Das für die Verbindung verwendete Windows-Konto bzw. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konto muss mindestens Mitglied der festen Datenbankrolle **db_owner** in der Veröffentlichungsdatenbank sein.</span><span class="sxs-lookup"><span data-stu-id="ef773-124">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must at minimum be a member of the **db_owner** fixed database role in the publication database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef773-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef773-125">See Also</span></span>  
 <span data-ttu-id="ef773-126">[Verwalten von Anmeldeinformationen und Kennwörtern bei der Replikation](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="ef773-126">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="ef773-127">[Sicherheitsmodell des Replikations-Agents](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="ef773-127">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="ef773-128">[Replikations-Agents (Übersicht)](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="ef773-128">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="ef773-129">Bewährte Methoden für die Replikationssicherheit</span><span class="sxs-lookup"><span data-stu-id="ef773-129">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
