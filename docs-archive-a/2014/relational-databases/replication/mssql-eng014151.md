---
title: MSSQL_ENG014151 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014151 error
ms.assetid: 54b45e70-46b3-4c7a-a5bf-06f6dd028ceb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2796451f6f681cfb0ce529ed44a946c34135649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608558"
---
# <a name="mssql_eng014151"></a><span data-ttu-id="abae2-102">MSSQL_ENG014151</span><span class="sxs-lookup"><span data-stu-id="abae2-102">MSSQL_ENG014151</span></span>
    
## <a name="message-details"></a><span data-ttu-id="abae2-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="abae2-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="abae2-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="abae2-104">Product Name</span></span>|<span data-ttu-id="abae2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="abae2-105">SQL Server</span></span>|  
|<span data-ttu-id="abae2-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="abae2-106">Event ID</span></span>|<span data-ttu-id="abae2-107">14151</span><span class="sxs-lookup"><span data-stu-id="abae2-107">14151</span></span>|  
|<span data-ttu-id="abae2-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="abae2-108">Event Source</span></span>|<span data-ttu-id="abae2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="abae2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="abae2-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="abae2-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="abae2-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="abae2-111">Symbolic Name</span></span>||  
|<span data-ttu-id="abae2-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="abae2-112">Message Text</span></span>|<span data-ttu-id="abae2-113">Replikations-%1!s!: Fehler beim %2!s!-Agent.</span><span class="sxs-lookup"><span data-stu-id="abae2-113">Replication-%s: agent %s failed.</span></span> <span data-ttu-id="abae2-114">%3!</span><span class="sxs-lookup"><span data-stu-id="abae2-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="abae2-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="abae2-115">Explanation</span></span>  
 <span data-ttu-id="abae2-116">Dieser Fehler wird bei allen Replikations-Agentfehlern ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="abae2-116">This error is raised for any replication agent failure.</span></span> <span data-ttu-id="abae2-117">Der Text am Ende der Fehlermeldung ist kontextbedingt.</span><span class="sxs-lookup"><span data-stu-id="abae2-117">The text at the end of the message depends on the context of the failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="abae2-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="abae2-118">User Action</span></span>  
 <span data-ttu-id="abae2-119">Dieser Fehler kann in verschiedenen Situationen auftreten. Verwenden Sie zu seiner Behebung ggf. folgende Methoden:</span><span class="sxs-lookup"><span data-stu-id="abae2-119">This error can occur in a number of situations; use the following approaches as necessary:</span></span>  
  
-   <span data-ttu-id="abae2-120">Starten Sie den Agent neu, um zu ermitteln, ob er nun fehlerfrei ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="abae2-120">Restart the failed agent to see if it will now run without failures.</span></span> <span data-ttu-id="abae2-121">Weitere Informationen finden Sie unter [Starten und Beenden eines Replikations-Agents &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) oder [Ausführbare Konzepte für die Programmierung von Replikations-Agents](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="abae2-121">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="abae2-122">Überprüfen Sie Agent- und Auftragsverlauf auf andere Fehler, die eventuell um dieselbe Zeit aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="abae2-122">Check the agent history and job history for other errors that occurred around the same time.</span></span> <span data-ttu-id="abae2-123">Informationen zum Anzeigen des Agent-Status und der Fehlerinformationen im Replikationsmonitor finden Sie unter [View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="abae2-123">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="abae2-124">Überprüfen Sie, dass die Konnektivität zwischen den Computern, auf die der Agent zugreift, funktioniert, und stellen Sie dann mithilfe eines Hilfsprogramms eine Verbindung mit den einzelnen Computern her, z. B. mit dem [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="abae2-124">Verify that basic connectivity is working between the computers accessed by the agent, and then connect to each computer with a utility like the [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span> <span data-ttu-id="abae2-125">Benutzen Sie zum Herstellen der Verbindungen dasselbe Konto wie der Agent.</span><span class="sxs-lookup"><span data-stu-id="abae2-125">When connecting, use the same account under which the agent makes connections.</span></span> <span data-ttu-id="abae2-126">Weitere Informationen zu den erforderlichen Berechtigungen für die einzelnen Agentkonten finden Sie unter [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="abae2-126">For more information about the permissions required by each agent account, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
-   <span data-ttu-id="abae2-127">Wenn der Fehler auftritt, während eine Momentaufnahme erstellt oder angewendet wird, überprüfen Sie die Dateien im Momentaufnahmeverzeichnis auf Fehler.</span><span class="sxs-lookup"><span data-stu-id="abae2-127">If the error occurs while creating or applying a snapshot, check the files in the snapshot directory for errors.</span></span>  
  
-   <span data-ttu-id="abae2-128">Wenn der Fehler weiterhin auftritt, erhöhen Sie die Protokollierungsstufe des Agents, und geben Sie eine Ausgabedatei für das Protokoll an.</span><span class="sxs-lookup"><span data-stu-id="abae2-128">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="abae2-129">Je nach Zusammenhang, in dem der Fehler auftritt, finden Sie hier möglicherweise die Schritte, die zum Fehler führen, und/oder weitere Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="abae2-129">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abae2-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="abae2-130">See Also</span></span>  
 <span data-ttu-id="abae2-131">[Verwaltung des Replikations-Agents](agents/replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="abae2-131">[Replication Agent Administration](agents/replication-agent-administration.md) </span></span>  
 <span data-ttu-id="abae2-132">[Fehler- und Ereignisreferenz &#40;Replikation&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="abae2-132">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="abae2-133">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="abae2-133">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="abae2-134">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="abae2-134">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="abae2-135">[Replication Merge Agent](agents/replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="abae2-135">[Replication Merge Agent](agents/replication-merge-agent.md) </span></span>  
 <span data-ttu-id="abae2-136">[Warteschlangenlese-Agent der Microsoft SQL Server-Replikation](agents/replication-queue-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="abae2-136">[Replication Queue Reader Agent](agents/replication-queue-reader-agent.md) </span></span>  
 [<span data-ttu-id="abae2-137">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="abae2-137">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
  
