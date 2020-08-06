---
title: MSSQL_ENG021075 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021075 error
ms.assetid: c8c29543-d1f6-49d5-b6c8-e8c3aa373090
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 20f2428038326681f5f8eb877e5c3017ced30f00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620288"
---
# <a name="mssql_eng021075"></a><span data-ttu-id="14c9c-102">MSSQL_ENG021075</span><span class="sxs-lookup"><span data-stu-id="14c9c-102">MSSQL_ENG021075</span></span>
    
## <a name="message-details"></a><span data-ttu-id="14c9c-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="14c9c-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="14c9c-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="14c9c-104">Product Name</span></span>|<span data-ttu-id="14c9c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="14c9c-105">SQL Server</span></span>|  
|<span data-ttu-id="14c9c-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="14c9c-106">Event ID</span></span>|<span data-ttu-id="14c9c-107">21075</span><span class="sxs-lookup"><span data-stu-id="14c9c-107">21075</span></span>|  
|<span data-ttu-id="14c9c-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="14c9c-108">Event Source</span></span>|<span data-ttu-id="14c9c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="14c9c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="14c9c-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="14c9c-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="14c9c-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="14c9c-111">Symbolic Name</span></span>||  
|<span data-ttu-id="14c9c-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="14c9c-112">Message Text</span></span>|<span data-ttu-id="14c9c-113">Die Anfangsmomentaufnahme für die %1!s!-Veröffentlichung ist noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="14c9c-113">The initial snapshot for publication '%s' is not yet available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="14c9c-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="14c9c-114">Explanation</span></span>  
 <span data-ttu-id="14c9c-115">Der Fehler MSSQL_ENG021075 wird ausgelöst, wenn der Verteilungs-Agent oder der Merge-Agent gestartet wird, bevor der Momentaufnahme-Agent mit dem Generieren der Momentaufnahme fertig ist.</span><span class="sxs-lookup"><span data-stu-id="14c9c-115">Error MSSQL_ENG021075 is raised if the Distribution Agent or Merge Agent is started before the Snapshot Agent has finished generating the snapshot.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14c9c-116">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="14c9c-116">User Action</span></span>  
 <span data-ttu-id="14c9c-117">Wenn der Momentaufnahme-Agent für die Veröffentlichung seit der Erstellung des Abonnements oder seit dem letzten erneuten Initialisieren des Abonnements nicht mehr gestartet wurde, starten Sie den Momentaufnahme-Agent, und lassen Sie ihn die Momentaufnahme fertig generieren, bevor Sie den Verteilungs-Agent oder den Merge-Agent starten.</span><span class="sxs-lookup"><span data-stu-id="14c9c-117">If the Snapshot Agent for the publication has not been started since the subscription was created, or if it has not been started since the last time you chose to reinitialize the subscription, start the Snapshot Agent and let it complete before starting the Distribution Agent or Merge Agent.</span></span> <span data-ttu-id="14c9c-118">Weitere Informationen finden Sie unter [Erstellen und Anwenden der Momentaufnahme](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="14c9c-118">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="14c9c-119">Wenn der Momentaufnahme-Agent die Momentaufnahme nicht fertig generiert, überprüfen Sie den Verlauf des Momentaufnahme-Agents auf Fehler, und sorgen Sie für deren Behebung.</span><span class="sxs-lookup"><span data-stu-id="14c9c-119">If the Snapshot Agent does not complete, check the Snapshot Agent history for errors and address them.</span></span> <span data-ttu-id="14c9c-120">Informationen zum Anzeigen des Agent-Status und der Fehlerinformationen im Replikationsmonitor finden Sie unter [View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="14c9c-120">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="14c9c-121">Wenn der Fehler weiterhin auftritt, erhöhen Sie die Protokollierungsstufe des Agents, und geben Sie eine Ausgabedatei für das Protokoll an.</span><span class="sxs-lookup"><span data-stu-id="14c9c-121">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="14c9c-122">Je nach Zusammenhang, in dem der Fehler auftritt, finden Sie hier möglicherweise die Schritte, die zum Fehler führen, und/oder weitere Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="14c9c-122">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14c9c-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14c9c-123">See Also</span></span>  
 [<span data-ttu-id="14c9c-124">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="14c9c-124">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
