---
title: Sicherheit für den Warteschlangenlese-Agent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.QRA.f1
helpviewer_keywords:
- Queue Reader Agent Security dialog box
ms.assetid: 77938da0-2afd-4455-8826-f4a6a9440cb3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 22a5e5751184b626ab1af86f01782a42028b5ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621473"
---
# <a name="queue-reader-agent-security"></a><span data-ttu-id="517f4-102">Sicherheit für den Warteschlangenlese-Agent</span><span class="sxs-lookup"><span data-stu-id="517f4-102">Queue Reader Agent Security</span></span>
  <span data-ttu-id="517f4-103">Im Dialogfeld **Sicherheit für den Warteschlangenlese-Agent** können Sie das [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Konto angeben, unter dem der Warteschlangenlese-Agent ausgeführt wird und Verbindungen mit dem Verteiler herstellt.</span><span class="sxs-lookup"><span data-stu-id="517f4-103">The **Queue Reader Agent Security** dialog box allows you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Queue Reader Agent runs and makes local connections to the Distributor.</span></span> <span data-ttu-id="517f4-104">Der Agent stellt mithilfe des im Dialogfeld **Verlegereigenschaften** (über das Dialogfeld **Verteilereigenschaften** verfügbar) angegebenen Kontos die Verbindung zum Verleger her. Der Agent stellt für das Abonnement mithilfe desselben Kontexts wie der Verteilungs-Agent die Verbindung mit dem Abonnenten her.</span><span class="sxs-lookup"><span data-stu-id="517f4-104">The agent connects to the Publisher using the account specified in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box); the agent connects to the Subscriber using the same context as the Distribution Agent for the subscription.</span></span> <span data-ttu-id="517f4-105">Weitere Informationen finden Sie unter [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="517f4-105">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="517f4-106">Das Konto muss für das angegebene Kennwort gültig sein.</span><span class="sxs-lookup"><span data-stu-id="517f4-106">The account must be valid with the correct password specified.</span></span> <span data-ttu-id="517f4-107">Konten und Kennwörter werden erst bei der Ausführung eines Agents überprüft.</span><span class="sxs-lookup"><span data-stu-id="517f4-107">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="517f4-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="517f4-108">Options</span></span>  
 <span data-ttu-id="517f4-109">**Prozesskonto**</span><span class="sxs-lookup"><span data-stu-id="517f4-109">**Process account**</span></span>  
 <span data-ttu-id="517f4-110">Geben Sie das Windows-Konto ein, unter dem der Warteschlangenlese-Agent auf dem Verteiler ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="517f4-110">Enter a Windows account under which the Queue Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="517f4-111">Das angegebene Windows-Konto muss mindestens ein Mitglied der festen Datenbankrolle **db_owner** in der Verteilungsdatenbank sein.</span><span class="sxs-lookup"><span data-stu-id="517f4-111">The Windows account you specify must at minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
 <span data-ttu-id="517f4-112">**Kennwort** und **Kennwort bestätigen**</span><span class="sxs-lookup"><span data-stu-id="517f4-112">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="517f4-113">In diese Felder geben Sie das Kennwort für das Windows-Konto ein.</span><span class="sxs-lookup"><span data-stu-id="517f4-113">Enter the password for the Windows account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="517f4-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="517f4-114">See Also</span></span>  
 <span data-ttu-id="517f4-115">[Verwalten von Anmeldeinformationen und Kennwörtern bei der Replikation](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="517f4-115">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="517f4-116">[Sicherheitsmodell des Replikations-Agents](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="517f4-116">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="517f4-117">[Replikations-Agents (Übersicht)](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="517f4-117">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="517f4-118">Bewährte Methoden für die Replikationssicherheit</span><span class="sxs-lookup"><span data-stu-id="517f4-118">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
