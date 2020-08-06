---
title: MSSQL_ENG024070 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG024070 error
ms.assetid: 23ac7e00-fab6-429b-9f85-2736a322aa65
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07fcfcb96b284d46d46f63af4a650f925ef2de73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697917"
---
# <a name="mssql_eng024070"></a><span data-ttu-id="4b771-102">MSSQL_ENG024070</span><span class="sxs-lookup"><span data-stu-id="4b771-102">MSSQL_ENG024070</span></span>
    
## <a name="message-details"></a><span data-ttu-id="4b771-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="4b771-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4b771-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="4b771-104">Product Name</span></span>|<span data-ttu-id="4b771-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4b771-105">SQL Server</span></span>|  
|<span data-ttu-id="4b771-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="4b771-106">Event ID</span></span>|<span data-ttu-id="4b771-107">24070</span><span class="sxs-lookup"><span data-stu-id="4b771-107">24070</span></span>|  
|<span data-ttu-id="4b771-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="4b771-108">Event Source</span></span>|<span data-ttu-id="4b771-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4b771-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4b771-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="4b771-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="4b771-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="4b771-111">Symbolic Name</span></span>||  
|<span data-ttu-id="4b771-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="4b771-112">Message Text</span></span>|<span data-ttu-id="4b771-113">Dem Client fehlt ein erforderliches Privileg.</span><span class="sxs-lookup"><span data-stu-id="4b771-113">A required privilege is not held by the client.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4b771-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="4b771-114">Explanation</span></span>  
 <span data-ttu-id="4b771-115">Es handelt sich um einen allgemeinen Fehler, der unabhängig von der Verwendung der Replikation ausgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="4b771-115">This is a general error that can be raised regardless of whether replication is being used.</span></span> <span data-ttu-id="4b771-116">Auf einem Server in einer Replikationstopologie tritt der Fehler im Allgemeinen auf, weil das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Dienstkonto mithilfe des [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Dienstkontroll-Managers anstelle des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Managers geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="4b771-116">For a server in a replication topology, the error is typically raised because the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account is changed by using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Service Control Manager instead of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="4b771-117">Wenn Sie versuchen, nach der Änderung des Dienstkontos einen Agentauftrag auszuführen, erzeugt dieser Auftrag möglicherweise einen Fehler, und es wird eine Fehlermeldung wie die folgende angezeigt:</span><span class="sxs-lookup"><span data-stu-id="4b771-117">When you try to run an agent job after changing the service account, the job might fail with an error message that is similar to the following:</span></span>  
  
 <span data-ttu-id="4b771-118">"Ausgeführt als Benutzer: \<UserAccount> .</span><span class="sxs-lookup"><span data-stu-id="4b771-118">"Executed as user: \<UserAccount>.</span></span> <span data-ttu-id="4b771-119">Replikations Momentaufnahme-Subsystem Replikation: Fehler beim Agent \<AgentName> .</span><span class="sxs-lookup"><span data-stu-id="4b771-119">Replication-Replication Snapshot Subsystem: agent \<AgentName> failed.</span></span> <span data-ttu-id="4b771-120">Ausgeführt als Benutzer: \<UserAccount> .</span><span class="sxs-lookup"><span data-stu-id="4b771-120">Executed as user: \<UserAccount>.</span></span> <span data-ttu-id="4b771-121">Dem Client fehlt ein erforderliches Privileg.</span><span class="sxs-lookup"><span data-stu-id="4b771-121">A required privilege is not held by the client.</span></span> <span data-ttu-id="4b771-122">Fehler bei Schritt.</span><span class="sxs-lookup"><span data-stu-id="4b771-122">The step failed.</span></span> <span data-ttu-id="4b771-123">`[SQLSTATE 42000] (Error 14151)`.</span><span class="sxs-lookup"><span data-stu-id="4b771-123">`[SQLSTATE 42000] (Error 14151)`.</span></span> <span data-ttu-id="4b771-124">Fehler bei Schritt."</span><span class="sxs-lookup"><span data-stu-id="4b771-124">The step failed."</span></span>  
  
 <span data-ttu-id="4b771-125">Dieses Problem tritt auf, weil der Windows-Dienstkontroll-Manager dem neuen Dienstkonto nicht die erforderlichen Berechtigungen für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent zuweisen kann.</span><span class="sxs-lookup"><span data-stu-id="4b771-125">This problem occurs because the Windows Service Control Manager cannot grant the required permissions to the new service account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4b771-126">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="4b771-126">User Action</span></span>  
 <span data-ttu-id="4b771-127">Verwenden Sie zum Ändern von Dienstkonten und Kennwörtern immer den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager anstelle des Windows-Dienstkontroll-Managers, um dieses Problem in Zukunft zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="4b771-127">To avoid this problem in the future, always use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager instead of the Windows Service Control Manager to change service accounts and passwords.</span></span>  
  
 <span data-ttu-id="4b771-128">Ändern Sie das Dienstkonto mithilfe des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Managers zurück in das ursprüngliche Konto, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="4b771-128">To resolve this problem, use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to change the service account back to the original account.</span></span> <span data-ttu-id="4b771-129">Verwenden Sie anschließend den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager, um das Dienstkonto in das neue Konto zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4b771-129">Then, use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to change to the new account.</span></span> <span data-ttu-id="4b771-130">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager fügt das neue Konto dann der folgenden Sicherheitsgruppe hinzu:</span><span class="sxs-lookup"><span data-stu-id="4b771-130">When you do this, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager adds the new account to the following security group:</span></span>  
  
 <span data-ttu-id="4b771-131">SQLServer2008SQLAgentUser$ComputerName$InstanceName</span><span class="sxs-lookup"><span data-stu-id="4b771-131">SQLServer2008SQLAgentUser$ComputerName$InstanceName</span></span>  
  
 <span data-ttu-id="4b771-132">Als Mitglied dieser Sicherheitsgruppe verfügt das neue Konto über die erforderlichen Berechtigungen, um den Auftrag des Replikations-Agents auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4b771-132">Being a member of this security group grants to the new account the required permissions to run the replication agent job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b771-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b771-133">See Also</span></span>  
 <span data-ttu-id="4b771-134">[Fehler- und Ereignisreferenz &#40;Replikation&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="4b771-134">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="4b771-135">[Verwalten von Anmeldeinformationen und Kennwörtern bei der Replikation](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="4b771-135">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 [<span data-ttu-id="4b771-136">SQL Server-Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="4b771-136">SQL Server Configuration Manager</span></span>](../sql-server-configuration-manager.md)  
  
  
