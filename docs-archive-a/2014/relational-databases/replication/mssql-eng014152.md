---
title: MSSQL_ENG014152 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014152 error
ms.assetid: 4215e2b1-cd30-441f-9671-9afc742adf6e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 615b9cf2996653d86c44d6e43a83e01e8287b110
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616499"
---
# <a name="mssql_eng014152"></a><span data-ttu-id="11c66-102">MSSQL_ENG014152</span><span class="sxs-lookup"><span data-stu-id="11c66-102">MSSQL_ENG014152</span></span>
    
## <a name="message-details"></a><span data-ttu-id="11c66-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="11c66-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="11c66-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="11c66-104">Product Name</span></span>|<span data-ttu-id="11c66-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="11c66-105">SQL Server</span></span>|  
|<span data-ttu-id="11c66-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="11c66-106">Event ID</span></span>|<span data-ttu-id="11c66-107">14152</span><span class="sxs-lookup"><span data-stu-id="11c66-107">14152</span></span>|  
|<span data-ttu-id="11c66-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="11c66-108">Event Source</span></span>|<span data-ttu-id="11c66-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="11c66-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="11c66-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="11c66-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="11c66-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="11c66-111">Symbolic Name</span></span>||  
|<span data-ttu-id="11c66-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="11c66-112">Message Text</span></span>|<span data-ttu-id="11c66-113">Replikations-%1!: %2! (Agent) ist für die Wiederholung geplant.</span><span class="sxs-lookup"><span data-stu-id="11c66-113">Replication-%s: agent %s scheduled for retry.</span></span> <span data-ttu-id="11c66-114">%3!</span><span class="sxs-lookup"><span data-stu-id="11c66-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="11c66-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="11c66-115">Explanation</span></span>  
 <span data-ttu-id="11c66-116">Der angegebene Replikations-Agent ist für die Wiederholung des angeforderten Vorgangs vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="11c66-116">The specified replication agent has been scheduled to retry the requested operation.</span></span> <span data-ttu-id="11c66-117">Der Prozess wird so lange wiederholt, bis die konfigurierte maximale Anzahl der Wiederholungsversuche für den Auftragsschritt erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="11c66-117">The process continues to retry until it reaches the configured maximum number of retry attempts for the job step.</span></span>  
  
 <span data-ttu-id="11c66-118">Eine Wiederholung wird normalerweise aus einem der folgenden Gründe ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="11c66-118">A retry typically occurs because of one of the following reasons:</span></span>  
  
-   <span data-ttu-id="11c66-119">Der **QueryTimeout** -Wert wird überschritten.</span><span class="sxs-lookup"><span data-stu-id="11c66-119">The **QueryTimeout** value is exceeded.</span></span>  
  
-   <span data-ttu-id="11c66-120">Der **LoginTimeout** -Wert wird überschritten.</span><span class="sxs-lookup"><span data-stu-id="11c66-120">The **LoginTimeout** value is exceeded.</span></span>  
  
-   <span data-ttu-id="11c66-121">Der Replikationsvorgang wurde als Deadlockopfer ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="11c66-121">The replication process was chosen as a deadlock victim.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="11c66-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="11c66-122">User Action</span></span>  
 <span data-ttu-id="11c66-123">Wenn die Wiederholungsmeldung nicht häufig angezeigt wird, ist keine Benutzeraktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="11c66-123">If the retry message is infrequent, no user action is required.</span></span>  
  
 <span data-ttu-id="11c66-124">Verwenden Sie [sp_help_jobstep](/sql/relational-databases/system-stored-procedures/sp-help-jobstep-transact-sql) , um die aktuelle Einstellung für die maximale Anzahl der Wiederholungen des Schritts **Führt den Agent aus** für den angegebenen Replikations-Agent anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="11c66-124">Use [sp_help_jobstep](/sql/relational-databases/system-stored-procedures/sp-help-jobstep-transact-sql) to view the current setting for the maximum number of times the **Run agent** step for the specified replication agent will retry.</span></span> <span data-ttu-id="11c66-125">Sie können den- **@retry_attempts** Parameter der gespeicherten Prozedur [sp_update_jobstep](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) verwenden, um die Häufigkeit zu ändern, mit der ein Auftrags Schritt erneut versucht wird.</span><span class="sxs-lookup"><span data-stu-id="11c66-125">You can use the **@retry_attempts** parameter of the [sp_update_jobstep](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) stored procedure to adjust the number of times a job step retries.</span></span>  
  
 <span data-ttu-id="11c66-126">Wenn die Wiederholungsmeldung häufig wieder angezeigt wird, beheben Sie das Problem anhand der Meldung, durch die die Wiederholung verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="11c66-126">If the retry message recurs frequently, troubleshoot the issue based on the message that is causing the retry.</span></span> <span data-ttu-id="11c66-127">Prüfen Sie den Verlauf des Agents auf Meldungen, mit denen angegeben wird, warum die Wiederholung ausgeführt werden musste.</span><span class="sxs-lookup"><span data-stu-id="11c66-127">Check the agent's history for messages that indicate why the retry had to be scheduled.</span></span> <span data-ttu-id="11c66-128">In einigen Fällen müssen Sie möglicherweise eine detailliertere Protokollierung für Ihren Replikations-Agent aktivieren.</span><span class="sxs-lookup"><span data-stu-id="11c66-128">In some cases you may have to enable more detailed logging for your replication agent.</span></span> <span data-ttu-id="11c66-129">Weitere Informationen zur Konfiguration der Protokollierung für die Replikation finden Sie im Microsoft Knowledge Base-Artikel [312292](https://support.microsoft.com/kb/312292).</span><span class="sxs-lookup"><span data-stu-id="11c66-129">For more information about how to configure logging for replication, see the Microsoft Knowledge Base article [312292](https://support.microsoft.com/kb/312292).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11c66-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11c66-130">See Also</span></span>  
 [<span data-ttu-id="11c66-131">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="11c66-131">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
