---
title: MSSQL_ENG021797 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021797 error
ms.assetid: 54d83a1e-43fd-449c-a2b2-fdda2609a534
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d33ade7e7eea9fa9e95453a5b232447f7b222b18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697929"
---
# <a name="mssql_eng021797"></a><span data-ttu-id="493c5-102">MSSQL_ENG021797</span><span class="sxs-lookup"><span data-stu-id="493c5-102">MSSQL_ENG021797</span></span>
    
## <a name="message-details"></a><span data-ttu-id="493c5-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="493c5-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="493c5-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="493c5-104">Product Name</span></span>|<span data-ttu-id="493c5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="493c5-105">SQL Server</span></span>|  
|<span data-ttu-id="493c5-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="493c5-106">Event ID</span></span>|<span data-ttu-id="493c5-107">21797</span><span class="sxs-lookup"><span data-stu-id="493c5-107">21797</span></span>|  
|<span data-ttu-id="493c5-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="493c5-108">Event Source</span></span>|<span data-ttu-id="493c5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="493c5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="493c5-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="493c5-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="493c5-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="493c5-111">Symbolic Name</span></span>||  
|<span data-ttu-id="493c5-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="493c5-112">Message Text</span></span>|<span data-ttu-id="493c5-113">„%s“ muss eine gültige Windows-Anmeldung der folgenden Form sein: "MACHINE Login" oder "DOMAIN Login".</span><span class="sxs-lookup"><span data-stu-id="493c5-113">'%s' must be a valid Windows Login in the form: 'MACHINE\Login' or 'DOMAIN\Login'.</span></span> <span data-ttu-id="493c5-114">Lesen Sie die Dokumentation zu '%3!s!'.</span><span class="sxs-lookup"><span data-stu-id="493c5-114">Please see the documentation for '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="493c5-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="493c5-115">Explanation</span></span>  
 <span data-ttu-id="493c5-116">Dieser Fehler wird von den folgenden gespeicherten Replikations Prozeduren ausgelöst, wenn der für den-Parameter angegebene Wert **@job_login** null oder ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="493c5-116">This error is raised by the following replication stored procedures if the value specified for the **@job_login** parameter is null or not valid.</span></span> <span data-ttu-id="493c5-117">Dieser Fehler kann auftreten, wenn ein Mitglied der festen Datenbankrolle **db_owner** Skripts aus vorherigen Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ausführt.</span><span class="sxs-lookup"><span data-stu-id="493c5-117">This error can occur if a member of the **db_owner** fixed database role runs scripts from previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="493c5-118">Das Sicherheitsmodell wurde in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]geändert, daher müssen die Skripts aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="493c5-118">The security model changed in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and these scripts must be updated.</span></span>  
  
-   [<span data-ttu-id="493c5-119">sp_addlogreader_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="493c5-119">sp_addlogreader_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql)  
  
-   [<span data-ttu-id="493c5-120">sp_addqreader_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="493c5-120">sp_addqreader_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql)  
  
-   [<span data-ttu-id="493c5-121">sp_addpublication_snapshot &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="493c5-121">sp_addpublication_snapshot &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpublication-snapshot-transact-sql)  
  
-   [<span data-ttu-id="493c5-122">sp_addpushsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="493c5-122">sp_addpushsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpushsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="493c5-123">sp_addpullsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="493c5-123">sp_addpullsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="493c5-124">sp_addmergepushsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="493c5-124">sp_addmergepushsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmergepushsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="493c5-125">sp_addmergepullsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="493c5-125">sp_addmergepullsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmergepullsubscription-agent-transact-sql)  
  
 <span data-ttu-id="493c5-126">Diese gespeicherten Prozeduren können von einem Mitglied der festen Serverrolle **sysadmin** auf dem entsprechenden Server bzw. einem Mitglied der festen Datenbankrolle **db_owner** in der entsprechenden Datenbank ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="493c5-126">These stored procedures can be executed by a member of the **sysadmin** fixed server role on the appropriate server or a member of the **db_owner** fixed database role in the appropriate database.</span></span> <span data-ttu-id="493c5-127">Jede gespeicherte Prozedur erstellt einen Agentauftrag, für den Sie das [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Konto angeben können, unter dem der Agent ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="493c5-127">The stored procedures each create an agent job and allow you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the agent runs.</span></span> <span data-ttu-id="493c5-128">Für Benutzer, die die Rolle **sysadmin** besitzen, werden Agentaufträge implizit erstellt, auch wenn kein Windows-Konto angegeben wird – sollte ein Konto angegeben werden, muss es jedoch gültig sein. Agents werden im Kontext des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienstkontos auf dem entsprechenden Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="493c5-128">For users in the **sysadmin** role, agent jobs are created implicitly even if a Windows account is not specified (if an account is specified, it must be valid); agents run under the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account at the appropriate server.</span></span> <span data-ttu-id="493c5-129">Das Festlegen eines Kontos ist zwar nicht erforderlich, aus Sicherheitsgründen empfiehlt es sich jedoch, ein separates Konto für jeden Agent anzugeben.</span><span class="sxs-lookup"><span data-stu-id="493c5-129">Although the account is not required, it is a security best practice to specify a separate account for the agents.</span></span> <span data-ttu-id="493c5-130">Weitere Informationen finden Sie unter [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="493c5-130">For more information, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="493c5-131">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="493c5-131">User Action</span></span>  
 <span data-ttu-id="493c5-132">Stellen Sie sicher, dass Sie ein gültiges Windows-Konto für den- **@job_login** Parameter jeder Prozedur angeben.</span><span class="sxs-lookup"><span data-stu-id="493c5-132">Ensure you specify a valid Windows account for the **@job_login** parameter of each procedure.</span></span> <span data-ttu-id="493c5-133">Wenn Sie Replikationsskripts aus vorherigen Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]übernehmen, aktualisieren Sie diese Skripts, sodass sie die für [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]erforderlichen gespeicherten Prozeduren und Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="493c5-133">If you have replication scripts from previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], update these scripts to include the stored procedures and parameters required by [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="493c5-134">Weitere Informationen finden Sie unter [Aktualisieren von Replikationsskripts &#40;Replikationsprogrammierung mit Transact-SQL&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="493c5-134">For more information, see [Upgrade Replication Scripts &#40;Replication Transact-SQL Programming&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="493c5-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="493c5-135">See Also</span></span>  
 [<span data-ttu-id="493c5-136">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="493c5-136">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
