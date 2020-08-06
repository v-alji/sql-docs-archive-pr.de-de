---
title: Sicherheitsrollenanforderungen für die Replikation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- security [SQL Server replication], roles
- roles [SQL Server], replication
ms.assetid: b324a80f-4319-4cb2-847b-1910c49d90e0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7eeea09a8dd580870b1d7d5514878172325fe9fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721247"
---
# <a name="security-role-requirements-for-replication"></a><span data-ttu-id="5de1f-102">Security Role Requirements for Replication</span><span class="sxs-lookup"><span data-stu-id="5de1f-102">Security Role Requirements for Replication</span></span>
  <span data-ttu-id="5de1f-103">Die Replikation schränkt auf der Basis der Rollen, die dem Benutzernamen des jeweiligen Benutzers zugeordnet sind, die Aktionen ein, die dieser Benutzer ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="5de1f-103">Replication restricts the specific actions that a user can perform based on the roles to which the user's login is mapped.</span></span> <span data-ttu-id="5de1f-104">Die Replikation hat der festen Serverrolle **sysadmin** , der festen Datenbankrolle **db_owner** und den Benutzernamen in der Veröffentlichungszugriffsliste bestimmte Berechtigungen erteilt.</span><span class="sxs-lookup"><span data-stu-id="5de1f-104">Replication has granted certain permissions to the **sysadmin** fixed server role, the **db_owner** fixed database role, and the logins in the publication access list (PAL).</span></span>  
  
## <a name="security-role-requirements-for-replication-setup"></a><span data-ttu-id="5de1f-105">Sicherheitsrollenanforderungen für die Einrichtung der Replikation</span><span class="sxs-lookup"><span data-stu-id="5de1f-105">Security Role Requirements for Replication Setup</span></span>  
 <span data-ttu-id="5de1f-106">Die folgende Tabelle gibt einen Überblick darüber, welche Authentifizierungsanforderungen für allgemeine Aufgaben bei der Einrichtung der Replikation erfüllt sein müssen:</span><span class="sxs-lookup"><span data-stu-id="5de1f-106">The following table summarizes the authentication level necessary for common replication setup tasks:</span></span>  
  
|<span data-ttu-id="5de1f-107">Einrichtungsaufgabe</span><span class="sxs-lookup"><span data-stu-id="5de1f-107">Setup task</span></span>|<span data-ttu-id="5de1f-108">Erforderliche Mitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="5de1f-108">Membership requirement</span></span>|  
|----------------|----------------------------|  
|<span data-ttu-id="5de1f-109">Aktivieren eines Verteilers, Verlegers bzw. Abonnenten</span><span class="sxs-lookup"><span data-stu-id="5de1f-109">Enable a Distributor, Publisher, or Subscriber.</span></span>|<span data-ttu-id="5de1f-110">**sysadmin** -Serverrolle auf dem Verleger</span><span class="sxs-lookup"><span data-stu-id="5de1f-110">**sysadmin** server role on the Publisher.</span></span>|  
|<span data-ttu-id="5de1f-111">Aktivieren einer Datenbank für die Replikation</span><span class="sxs-lookup"><span data-stu-id="5de1f-111">Enable a database for replication.</span></span>|<span data-ttu-id="5de1f-112">**sysadmin** -Serverrolle auf dem Verleger</span><span class="sxs-lookup"><span data-stu-id="5de1f-112">**sysadmin** server role on the Publisher.</span></span>|  
|<span data-ttu-id="5de1f-113">Erstellen einer Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="5de1f-113">Create a publication.</span></span>|<span data-ttu-id="5de1f-114">**db_owner** -Datenbankrolle in der Veröffentlichungsdatenbank auf dem Verleger bzw. **sysadmin** -Serverrolle auf dem Verleger</span><span class="sxs-lookup"><span data-stu-id="5de1f-114">**db_owner** database role on the publication database at the Publisher or **sysadmin** server role on the Publisher.</span></span>|  
|<span data-ttu-id="5de1f-115">Anzeigen von Veröffentlichungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="5de1f-115">View publication properties.</span></span>|<span data-ttu-id="5de1f-116">Mitglied der Veröffentlichungszugriffsliste auf dem Verleger, **db_owner** -Datenbankrolle in der Veröffentlichungsdatenbank auf dem Verleger bzw. **sysadmin** -Serverrolle auf dem Verleger</span><span class="sxs-lookup"><span data-stu-id="5de1f-116">Member of the PAL at the Publisher, **db_owner** database role on the publication database at the Publisher, or **sysadmin** server role on the Publisher.</span></span>|  
|<span data-ttu-id="5de1f-117">Erstellen eines Abonnements</span><span class="sxs-lookup"><span data-stu-id="5de1f-117">Create a subscription.</span></span>|<span data-ttu-id="5de1f-118">**db_owner** -Datenbankrolle in der Veröffentlichungsdatenbank auf dem Verleger bzw. **sysadmin** -Serverrolle auf dem Verleger</span><span class="sxs-lookup"><span data-stu-id="5de1f-118">**db_owner** database role on the publication database at the Publisher or **sysadmin** server role on the Publisher.</span></span><br /><br /> <span data-ttu-id="5de1f-119">**db_owner** -Datenbankrolle in der Abonnementdatenbank auf dem Abonnenten bzw. **sysadmin** -Serverrolle auf dem Abonnenten</span><span class="sxs-lookup"><span data-stu-id="5de1f-119">**db_owner** database role on the subscription database at the Subscriber or **sysadmin** server role on the Subscriber.</span></span>|  
|<span data-ttu-id="5de1f-120">Konfigurieren von Agentprofilen</span><span class="sxs-lookup"><span data-stu-id="5de1f-120">Configure agent profiles.</span></span>|<span data-ttu-id="5de1f-121">**sysadmin** -Serverrolle auf dem Verteiler</span><span class="sxs-lookup"><span data-stu-id="5de1f-121">**sysadmin** server role on the Distributor.</span></span>|  
  
## <a name="security-role-requirements-for-replication-maintenance"></a><span data-ttu-id="5de1f-122">Sicherheitsrollenanforderungen für die Replikationswartung</span><span class="sxs-lookup"><span data-stu-id="5de1f-122">Security Role Requirements for Replication Maintenance</span></span>  
 <span data-ttu-id="5de1f-123">Die folgende Tabelle gibt einen Überblick darüber, welche Authentifizierungsanforderungen für allgemeine Aufgaben bei der Wartung der Replikation erfüllt sein müssen:</span><span class="sxs-lookup"><span data-stu-id="5de1f-123">The following table summarizes the authentication level necessary for common replication maintenance tasks:</span></span>  
  
|<span data-ttu-id="5de1f-124">Wartungsaufgabe</span><span class="sxs-lookup"><span data-stu-id="5de1f-124">Maintenance task</span></span>|<span data-ttu-id="5de1f-125">Erforderliche Mitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="5de1f-125">Membership requirement</span></span>|  
|----------------------|----------------------------|  
|<span data-ttu-id="5de1f-126">Ändern oder Löschen eines Verteilers, Verlegers bzw. Abonnenten</span><span class="sxs-lookup"><span data-stu-id="5de1f-126">Modify or drop a Distributor, Publisher, or Subscriber.</span></span>|<span data-ttu-id="5de1f-127">**sysadmin** -Serverrolle auf dem entsprechenden Server</span><span class="sxs-lookup"><span data-stu-id="5de1f-127">**sysadmin** server role on the appropriate server.</span></span>|  
|<span data-ttu-id="5de1f-128">Ändern oder Löschen einer Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="5de1f-128">Modify or drop a publication.</span></span>|<span data-ttu-id="5de1f-129">**db_owner** -Datenbankrolle in der Veröffentlichungsdatenbank auf dem Verleger bzw. **sysadmin** -Serverrolle auf dem Verleger</span><span class="sxs-lookup"><span data-stu-id="5de1f-129">**db_owner** database role on the publication database at the Publisher or **sysadmin** server role on the Publisher.</span></span>|  
|<span data-ttu-id="5de1f-130">Ändern oder Löschen eines Abonnements auf dem Verleger</span><span class="sxs-lookup"><span data-stu-id="5de1f-130">Modify or drop a subscription at the Publisher.</span></span>|<span data-ttu-id="5de1f-131">**db_owner** -Datenbankrolle in der Veröffentlichungsdatenbank auf dem Verleger bzw. **sysadmin** -Serverrolle auf dem Verleger</span><span class="sxs-lookup"><span data-stu-id="5de1f-131">**db_owner** database role on the publication database at the Publisher or **sysadmin** server role on the Publisher.</span></span>|  
|<span data-ttu-id="5de1f-132">Ändern oder Löschen eines Abonnements auf dem Abonnenten</span><span class="sxs-lookup"><span data-stu-id="5de1f-132">Modify or drop a subscription at the Subscriber.</span></span>|<span data-ttu-id="5de1f-133">**db_owner** -Datenbankrolle in der Abonnementdatenbank auf dem Abonnenten bzw. **sysadmin** -Serverrolle auf dem Abonnenten</span><span class="sxs-lookup"><span data-stu-id="5de1f-133">**db_owner** database role on the subscription database at the Subscriber or **sysadmin** server role on the Subscriber.</span></span>|  
|<span data-ttu-id="5de1f-134">Markieren eines Abonnements für die Neuinitialisierung</span><span class="sxs-lookup"><span data-stu-id="5de1f-134">Mark a subscription for reinitialization.</span></span>|<span data-ttu-id="5de1f-135">Pushabonnement: **db_owner** -Datenbankrolle in der Veröffentlichungsdatenbank auf dem Verleger bzw. **sysadmin** -Serverrolle auf dem Verleger.</span><span class="sxs-lookup"><span data-stu-id="5de1f-135">Push subscription: **db_owner** database role in the publication database at the Publisher or **sysadmin** server role on the Publisher.</span></span><br /><br /> <span data-ttu-id="5de1f-136">Pullabonnement: **db_owner** -Datenbankrolle in der Abonnementdatenbank auf dem Abonnenten bzw. **sysadmin** -Serverrolle auf dem Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="5de1f-136">Pull subscription: **db_owner** database role in the subscription database at the Subscriber or **sysadmin** server role on the Subscriber.</span></span>|  
|<span data-ttu-id="5de1f-137">Anzeigen der Replikationsaktivität, der Fehler und des Verlaufs mithilfe des Replikationsmonitors.</span><span class="sxs-lookup"><span data-stu-id="5de1f-137">View replication activity, errors, and history using Replication Monitor.</span></span> <span data-ttu-id="5de1f-138">Ein Benutzer kann Agentprofile, Zeitpläne usw. nicht ändern, wenn er nicht Mitglied der **sysadmin** -Serverrolle ist.</span><span class="sxs-lookup"><span data-stu-id="5de1f-138">A user cannot modify agent profiles, schedules, and so on, unless the user is a member of the **sysadmin** server role.</span></span>|<span data-ttu-id="5de1f-139">**replmonitor** -Datenbankrolle in der Verteilungsdatenbank auf dem Verteiler bzw. **sysadmin** -Serverrolle auf dem Verteiler</span><span class="sxs-lookup"><span data-stu-id="5de1f-139">**replmonitor** database role on the distribution database at the Distributor or **sysadmin** server role on the Distributor.</span></span>|  
|<span data-ttu-id="5de1f-140">Warten von Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="5de1f-140">Maintain replication agents.</span></span>|<span data-ttu-id="5de1f-141">**db_owner** -Datenbankrolle in der entsprechenden Datenbank bzw. **sysadmin** -Serverrolle auf dem entsprechenden Server</span><span class="sxs-lookup"><span data-stu-id="5de1f-141">**db_owner** database role in the appropriate database or **sysadmin** server role on the appropriate server.</span></span><br /><br /> <span data-ttu-id="5de1f-142">Wenn der Agent von einem Benutzer in der **sysadmin** -Rolle erstellt wurde und für den Agent kein Proxykonto angegeben wurde, wird der Agent im Kontext des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Agent-Kontos ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5de1f-142">If the agent was created by a user in the **sysadmin** role, and a proxy account was not specified for the agent, the agent runs under the context of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent account.</span></span> <span data-ttu-id="5de1f-143">In diesem Fall können Benutzer mit der **db_owner** -Rolle den dem Agent zugewiesenen Auftrag nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="5de1f-143">In this case, a user in the **db_owner** role cannot modify the job associated with the agent.</span></span>|  
|<span data-ttu-id="5de1f-144">Starten oder Beenden eines Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="5de1f-144">Start or stop a replication agent.</span></span>|<span data-ttu-id="5de1f-145">Besitzer des Agentauftrags bzw. der **sysadmin** -Serverrolle auf dem entsprechenden Server.</span><span class="sxs-lookup"><span data-stu-id="5de1f-145">Owner of the agent job or **sysadmin** server role on the appropriate server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5de1f-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5de1f-146">See Also</span></span>  
 <span data-ttu-id="5de1f-147">[Replication Security Best Practices](replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="5de1f-147">[Replication Security Best Practices](replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="5de1f-148">SQL Server-Replikation Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5de1f-148">SQL Server Replication Security</span></span>](view-and-modify-replication-security-settings.md)  
  
  