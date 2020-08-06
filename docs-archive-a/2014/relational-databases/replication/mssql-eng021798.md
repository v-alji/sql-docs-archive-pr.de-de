---
title: MSSQL_ENG021798 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021798 error
ms.assetid: 596f5092-75ab-4a19-8582-588687c7b089
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 327b4a373c28376701ea12400215ab00367df66a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697923"
---
# <a name="mssql_eng021798"></a><span data-ttu-id="2ec1e-102">MSSQL_ENG021798</span><span class="sxs-lookup"><span data-stu-id="2ec1e-102">MSSQL_ENG021798</span></span>
    
## <a name="message-details"></a><span data-ttu-id="2ec1e-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="2ec1e-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ec1e-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="2ec1e-104">Product Name</span></span>|<span data-ttu-id="2ec1e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2ec1e-105">SQL Server</span></span>|  
|<span data-ttu-id="2ec1e-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2ec1e-106">Event ID</span></span>|<span data-ttu-id="2ec1e-107">21798</span><span class="sxs-lookup"><span data-stu-id="2ec1e-107">21798</span></span>|  
|<span data-ttu-id="2ec1e-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="2ec1e-108">Event Source</span></span>|<span data-ttu-id="2ec1e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2ec1e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2ec1e-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="2ec1e-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="2ec1e-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="2ec1e-111">Symbolic Name</span></span>||  
|<span data-ttu-id="2ec1e-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="2ec1e-112">Message Text</span></span>|<span data-ttu-id="2ec1e-113">Der '%s'-Agent-Auftrag muss vor dem Fortsetzen des Vorgangs über '%s' hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2ec1e-113">The '%s' agent job must be added through '%s' before continuing.</span></span> <span data-ttu-id="2ec1e-114">Lesen Sie die Dokumentation zu '%3!s!'.</span><span class="sxs-lookup"><span data-stu-id="2ec1e-114">Please see the documentation for '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2ec1e-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="2ec1e-115">Explanation</span></span>  
 <span data-ttu-id="2ec1e-116">Um eine Veröffentlichung erstellen zu können, müssen Sie ein Mitglied der festen Serverrolle **sysadmin** auf dem Verleger oder ein Mitglied der festen Datenbankrolle **db_owner** in der Veröffentlichungsdatenbank sein.</span><span class="sxs-lookup"><span data-stu-id="2ec1e-116">To create a publication, you must be a member of the **sysadmin** fixed server role on the Publisher or a member of the **db_owner** fixed database role in the publication database.</span></span> <span data-ttu-id="2ec1e-117">Wenn Sie ein Mitglied der **db_owner** -Rolle sind, wird dieser Fehler in folgenden Situationen ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="2ec1e-117">If you are a member of the **db_owner** role, this error is raised if:</span></span>  
  
-   <span data-ttu-id="2ec1e-118">Sie führen Skripts von [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]aus.</span><span class="sxs-lookup"><span data-stu-id="2ec1e-118">You run scripts from [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="2ec1e-119">Das Sicherheitsmodell wurde in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]geändert, daher müssen die Skripts aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2ec1e-119">The security model changed in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and these scripts must be updated.</span></span>  
  
-   <span data-ttu-id="2ec1e-120">Die gespeicherte Prozedur **sp_addpublication** wird vor [sp_addlogreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2ec1e-120">The stored procedure **sp_addpublication** is executed before executing [sp_addlogreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql).</span></span> <span data-ttu-id="2ec1e-121">Dies gilt für alle Transaktionsveröffentlichungen.</span><span class="sxs-lookup"><span data-stu-id="2ec1e-121">This applies to all transactional publications.</span></span>  
  
-   <span data-ttu-id="2ec1e-122">Die gespeicherte Prozedur **sp_addpublication** wird vor [sp_addqreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2ec1e-122">The stored procedure **sp_addpublication** is executed before executing [sp_addqreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql).</span></span> <span data-ttu-id="2ec1e-123">Dies gilt für Transaktions Veröffentlichungen, die für Abonnements mit verzögertem Update über eine Warteschlange aktiviert sind (der Wert true für den- **@allow_queued_tran** Parameter von **sp_addpublication**).</span><span class="sxs-lookup"><span data-stu-id="2ec1e-123">This applies to transactional publications that are enabled for queued updating subscriptions (a value of TRUE for the **@allow_queued_tran** parameter of **sp_addpublication**).</span></span>  
  
 <span data-ttu-id="2ec1e-124">Die gespeicherten Prozeduren **sp_addlogreader_agent** und **sp_addqreader_agent** erstellen jeweils einen Agentauftrag und ermöglichen Ihnen, das [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Konto anzugeben, unter dem der Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2ec1e-124">The stored procedures **sp_addlogreader_agent** and **sp_addqreader_agent** each create an agent job and allow you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the agent runs.</span></span> <span data-ttu-id="2ec1e-125">Für Benutzer, die die Rolle **sysadmin** besitzen, werden Agentaufträge implizit erstellt, wenn **sp_addlogreader_agent** und **sp_addqreader_agent** nicht ausgeführt werden. Die Agents werden im Kontext des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienstkontos auf dem Verteiler ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2ec1e-125">For users in the **sysadmin** role, agent jobs are created implicitly if **sp_addlogreader_agent** and **sp_addqreader_agent** are not executed; agents run under the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account at the Distributor.</span></span> <span data-ttu-id="2ec1e-126">Obwohl **sp_addlogreader_agent** und **sp_addqreader_agent** für Benutzer in der **sysadmin** -Rolle nicht erforderlich sind, empfiehlt sich als bewährte Sicherheitsmethode, ein separates Konto für die Agents anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2ec1e-126">Although **sp_addlogreader_agent** and **sp_addqreader_agent** are not required for users in the **sysadmin** role, it is a security best practice to specify a separate account for the agents.</span></span> <span data-ttu-id="2ec1e-127">Weitere Informationen finden Sie unter [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="2ec1e-127">For more information, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2ec1e-128">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="2ec1e-128">User Action</span></span>  
 <span data-ttu-id="2ec1e-129">Stellen Sie sicher, dass Sie die Prozeduren in der richtigen Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="2ec1e-129">Ensure you execute procedures in the correct order.</span></span> <span data-ttu-id="2ec1e-130">Weitere Informationen finden Sie unter [Erstellen einer Veröffentlichung](publish/create-a-publication.md), Aktualisieren dieser Skripts, um die für und spätere Versionen erforderlichen gespeicherten Prozeduren und Parameter einzuschließen [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2ec1e-130">For more information, see [Create a Publication](publish/create-a-publication.md), update these scripts to include the stored procedures and parameters required by [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="2ec1e-131">Weitere Informationen finden Sie unter [Aktualisieren von Replikationsskripts &#40;Replikationsprogrammierung mit Transact-SQL&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="2ec1e-131">For more information, see [Upgrade Replication Scripts &#40;Replication Transact-SQL Programming&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec1e-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2ec1e-132">See Also</span></span>  
 [<span data-ttu-id="2ec1e-133">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="2ec1e-133">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
