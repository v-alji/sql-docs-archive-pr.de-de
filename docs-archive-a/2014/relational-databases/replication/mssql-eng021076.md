---
title: MSSQL_ENG021076 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021076 error
ms.assetid: 612e5c59-ba3e-49c3-a3df-56bac3d850a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4161428767ce78726436c0cf794f5250140d35b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697946"
---
# <a name="mssql_eng021076"></a><span data-ttu-id="d1ad5-102">MSSQL_ENG021076</span><span class="sxs-lookup"><span data-stu-id="d1ad5-102">MSSQL_ENG021076</span></span>
    
## <a name="message-details"></a><span data-ttu-id="d1ad5-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="d1ad5-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d1ad5-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="d1ad5-104">Product Name</span></span>|<span data-ttu-id="d1ad5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d1ad5-105">SQL Server</span></span>|  
|<span data-ttu-id="d1ad5-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="d1ad5-106">Event ID</span></span>|<span data-ttu-id="d1ad5-107">21076</span><span class="sxs-lookup"><span data-stu-id="d1ad5-107">21076</span></span>|  
|<span data-ttu-id="d1ad5-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="d1ad5-108">Event Source</span></span>|<span data-ttu-id="d1ad5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d1ad5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d1ad5-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="d1ad5-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="d1ad5-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="d1ad5-111">Symbolic Name</span></span>||  
|<span data-ttu-id="d1ad5-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d1ad5-112">Message Text</span></span>|<span data-ttu-id="d1ad5-113">Die Anfangsmomentaufnahme für den %1!s!-Artikel ist noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d1ad5-113">The initial snapshot for article '%s' is not yet available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d1ad5-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d1ad5-114">Explanation</span></span>  
 <span data-ttu-id="d1ad5-115">Der Fehler MSSQL_ENG021076 wird ausgelöst, wenn der Verteilungs-Agent gestartet wird, bevor der Momentaufnahme-Agent mit dem Generieren der Momentaufnahmen fertig ist.</span><span class="sxs-lookup"><span data-stu-id="d1ad5-115">Error MSSQL_ENG021076 can be raised if the Distribution Agent is started before the Snapshot Agent has finished generating the snapshot.</span></span> <span data-ttu-id="d1ad5-116">Dieser Fehler wird nur ausgelöst, wenn die Veröffentlichung einen einzigen Artikel enthält.</span><span class="sxs-lookup"><span data-stu-id="d1ad5-116">This error is raised only if the publication contains a single article.</span></span> <span data-ttu-id="d1ad5-117">Wenn die Veröffentlichung mehr als einen Artikel enthält, wird stattdessen der Fehler MSSQL_ENG021075 ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d1ad5-117">If the publication contains more than one article, MSSQL_ENG021075 is raised instead.</span></span> <span data-ttu-id="d1ad5-118">Weitere Informationen finden Sie unter [MSSQL_ENG021075](mssql-eng021075.md).</span><span class="sxs-lookup"><span data-stu-id="d1ad5-118">For more information, see [MSSQL_ENG021075](mssql-eng021075.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d1ad5-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d1ad5-119">User Action</span></span>  
 <span data-ttu-id="d1ad5-120">Wenn der Momentaufnahme-Agent für die Veröffentlichung seit der Erstellung des Abonnements oder seit dem letzten erneuten Initialisieren des Abonnements nicht mehr gestartet wurde, starten Sie den Momentaufnahme-Agent, und lassen Sie ihn die Momentaufnahme fertig generieren, bevor Sie den Verteilungs-Agent starten.</span><span class="sxs-lookup"><span data-stu-id="d1ad5-120">If the Snapshot Agent for the publication has not been started since the subscription was created, or if it has not been started since the last time you chose to reinitialize the subscription, start the Snapshot Agent and let it complete before starting the Distribution Agent.</span></span> <span data-ttu-id="d1ad5-121">Weitere Informationen finden Sie unter [Erstellen und Anwenden der Momentaufnahme](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="d1ad5-121">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="d1ad5-122">Wenn der Momentaufnahme-Agent die Momentaufnahme nicht fertig generiert, überprüfen Sie den Verlauf des Momentaufnahme-Agents auf Fehler, und sorgen Sie für deren Behebung.</span><span class="sxs-lookup"><span data-stu-id="d1ad5-122">If the Snapshot Agent does not complete, check the Snapshot Agent history for errors and address them.</span></span> <span data-ttu-id="d1ad5-123">Informationen zum Anzeigen des Agent-Status und der Fehlerinformationen im Replikationsmonitor finden Sie unter [View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="d1ad5-123">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="d1ad5-124">Wenn der Fehler weiterhin auftritt, erhöhen Sie die Protokollierungsstufe des Agents, und geben Sie eine Ausgabedatei für das Protokoll an.</span><span class="sxs-lookup"><span data-stu-id="d1ad5-124">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="d1ad5-125">Je nach Zusammenhang, in dem der Fehler auftritt, finden Sie hier möglicherweise die Schritte, die zum Fehler führen, und/oder weitere Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="d1ad5-125">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1ad5-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d1ad5-126">See Also</span></span>  
 [<span data-ttu-id="d1ad5-127">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="d1ad5-127">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
