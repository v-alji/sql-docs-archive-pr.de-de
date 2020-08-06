---
title: MSSQL_ENG020557 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020557 error
ms.assetid: c43c6952-5b60-4347-b881-11a0004dce24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 45c24d453eb95abaa967ae65ceb5934b7dee969e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622592"
---
# <a name="mssql_eng020557"></a><span data-ttu-id="e50b3-102">MSSQL_ENG020557</span><span class="sxs-lookup"><span data-stu-id="e50b3-102">MSSQL_ENG020557</span></span>
    
## <a name="message-details"></a><span data-ttu-id="e50b3-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="e50b3-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e50b3-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="e50b3-104">Product Name</span></span>|<span data-ttu-id="e50b3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e50b3-105">SQL Server</span></span>|  
|<span data-ttu-id="e50b3-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e50b3-106">Event ID</span></span>|<span data-ttu-id="e50b3-107">20557</span><span class="sxs-lookup"><span data-stu-id="e50b3-107">20557</span></span>|  
|<span data-ttu-id="e50b3-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="e50b3-108">Event Source</span></span>|<span data-ttu-id="e50b3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e50b3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e50b3-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="e50b3-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="e50b3-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="e50b3-111">Symbolic Name</span></span>||  
|<span data-ttu-id="e50b3-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="e50b3-112">Message Text</span></span>|<span data-ttu-id="e50b3-113">Der Agent wird heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="e50b3-113">Agent shutdown.</span></span> <span data-ttu-id="e50b3-114">Weitere Informationen finden Sie im Auftragsverlauf des SQL Server-Agents für den Auftrag '%s'.</span><span class="sxs-lookup"><span data-stu-id="e50b3-114">For more information, see the SQL Server Agent job history for job '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e50b3-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="e50b3-115">Explanation</span></span>  
 <span data-ttu-id="e50b3-116">Ein Replikations-Agent wurde beendet, ohne dass ein Grund in die entsprechende Verlaufstabelle geschrieben wurde, oder der Agent wurde während eines Prozesses beendet.</span><span class="sxs-lookup"><span data-stu-id="e50b3-116">A replication agent has shut down without writing a reason to the appropriate history table, or the agent was shut down while in the middle of a process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e50b3-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="e50b3-117">User Action</span></span>  
  
-   <span data-ttu-id="e50b3-118">Starten Sie den Agent neu, um zu ermitteln, ob er nun fehlerfrei ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e50b3-118">Restart the agent to see whether it will now run without failures.</span></span> <span data-ttu-id="e50b3-119">Weitere Informationen finden Sie unter [Starten und Beenden eines Replikations-Agents &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) oder [Ausführbare Konzepte für die Programmierung von Replikations-Agents](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="e50b3-119">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="e50b3-120">Überprüfen Sie Agent- und Auftragsverlauf auf andere Fehler, die eventuell um dieselbe Zeit aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="e50b3-120">Check the agent history and job history for other errors that occurred around the same time.</span></span> <span data-ttu-id="e50b3-121">Informationen zum Anzeigen des Agent-Status und der Fehlerinformationen im Replikationsmonitor finden Sie unter [View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="e50b3-121">For information about how to view agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>
-   <span data-ttu-id="e50b3-122">Stellen Sie sicher, dass die Konnektivität zwischen den Computern, auf die der Agent zugreift, funktioniert, und stellen Sie dann mithilfe eines Hilfsprogramms eine Verbindung mit den einzelnen Computern her, z. B. mithilfe des Hilfsprogramms **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="e50b3-122">Verify that basic connectivity is working between the computers that are accessed by the agent, and then connect to each computer by using a utility, such as the **sqlcmd** utility.</span></span> <span data-ttu-id="e50b3-123">Benutzen Sie zum Herstellen der Verbindungen dasselbe Konto wie der Agent.</span><span class="sxs-lookup"><span data-stu-id="e50b3-123">When you connect, use the same account under which the agent makes connections.</span></span> <span data-ttu-id="e50b3-124">Weitere Informationen zu den erforderlichen Berechtigungen für die einzelnen Agentkonten finden Sie unter [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="e50b3-124">For more information about the permissions that are required by each agent account, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
-   <span data-ttu-id="e50b3-125">Wenn der Fehler auftritt, während Sie eine Momentaufnahme erstellen oder anwenden, überprüfen Sie die Dateien im Momentaufnahmeverzeichnis auf Fehler.</span><span class="sxs-lookup"><span data-stu-id="e50b3-125">If the error occurs while you are creating or applying a snapshot, check the files in the snapshot directory for errors.</span></span>  
  
-   <span data-ttu-id="e50b3-126">Wenn der Fehler weiterhin auftritt, erhöhen Sie die Protokollierungsstufe des Agents, und geben Sie eine Ausgabedatei für das Protokoll an.</span><span class="sxs-lookup"><span data-stu-id="e50b3-126">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="e50b3-127">Je nach Zusammenhang, in dem der Fehler auftritt, finden Sie hier möglicherweise die Schritte, die zum Fehler führen, und weitere Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="e50b3-127">Depending on the context of the error, this could provide the steps leading up to the error and additional error messages.</span></span> <span data-ttu-id="e50b3-128">Weitere Informationen zur Konfiguration der Protokollierung für die Replikation finden Sie im Microsoft Knowledge Base-Artikel [312292](https://support.microsoft.com/kb/312292).</span><span class="sxs-lookup"><span data-stu-id="e50b3-128">For more information about how to configure logging for replication, see the Microsoft Knowledge Base article [312292](https://support.microsoft.com/kb/312292).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e50b3-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e50b3-129">See Also</span></span>  
 [<span data-ttu-id="e50b3-130">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="e50b3-130">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
