---
title: MSSQL_REPL027056 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL027056 error
ms.assetid: 92d62f3c-b8ae-482e-a348-2e9a8ee9786e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44fb130321ec54c39559d52e493cc8f3424172fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721346"
---
# <a name="mssql_repl027056"></a><span data-ttu-id="33837-102">MSSQL_REPL027056</span><span class="sxs-lookup"><span data-stu-id="33837-102">MSSQL_REPL027056</span></span>
    
## <a name="message-details"></a><span data-ttu-id="33837-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="33837-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="33837-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="33837-104">Product Name</span></span>|<span data-ttu-id="33837-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="33837-105">SQL Server</span></span>|  
|<span data-ttu-id="33837-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="33837-106">Event ID</span></span>|<span data-ttu-id="33837-107">27056</span><span class="sxs-lookup"><span data-stu-id="33837-107">27056</span></span>|  
|<span data-ttu-id="33837-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="33837-108">Event Source</span></span>|<span data-ttu-id="33837-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="33837-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="33837-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="33837-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="33837-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="33837-111">Symbolic Name</span></span>||  
|<span data-ttu-id="33837-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="33837-112">Message Text</span></span>|<span data-ttu-id="33837-113">Vom Mergeprozess konnte der Generierungsverlauf auf '%1' nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="33837-113">The merge process was unable to change generation history at the '%1'.</span></span> <span data-ttu-id="33837-114">Führen Sie zur Problembehandlung einen Neustart der Synchronisierung mit ausführlicher Verlaufsprotokollierung aus, und geben Sie eine Ausgabedatei an, in die geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="33837-114">When troubleshooting, restart the synchronization with verbose history logging and specify an output file to which to write.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="33837-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="33837-115">Explanation</span></span>  
 <span data-ttu-id="33837-116">Dieser Fehler wird in der Regel als Folge eine Konflikts in Systemtabellen der Mergereplikation ausgelöst, die extrem groß geworden sind.</span><span class="sxs-lookup"><span data-stu-id="33837-116">This error is typically raised as a result of contention in merge replication system tables that have grown excessively large.</span></span> <span data-ttu-id="33837-117">Meistens entstehen große Systemtabellen aufgrund einer langen Beibehaltungsdauer von Veröffentlichungen, da Metadaten bis zum Ablauf der Beibehaltungsdauer gespeichert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="33837-117">Large system tables are typically caused by a long publication retention period, because metadata must be stored in these tables until the retention period is reached.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="33837-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="33837-118">User Action</span></span>  
 <span data-ttu-id="33837-119">**So lösen Sie das Problem:**</span><span class="sxs-lookup"><span data-stu-id="33837-119">**To resolve the issue:**</span></span>  
  
1.  <span data-ttu-id="33837-120">Verringern Sie den Wert der Parameter -**DownloadGenerationsPerBatch** und **-UploadGenerationsPerBatch** für den Merge-Agent, damit die Verarbeitung fortgesetzt werden kann und Sie sich der eigentlichen Ursache des Fehlers widmen können.</span><span class="sxs-lookup"><span data-stu-id="33837-120">Decrease the value of the -**DownloadGenerationsPerBatch** and **-UploadGenerationsPerBatch** parameters for the Merge Agent to allow processing to continue while you address the underlying issue causing the error.</span></span> <span data-ttu-id="33837-121">Agentparameter können in den Agentprofilen und in der Befehlszeile angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="33837-121">Agent parameters can be specified in agent profiles and on the command line.</span></span> <span data-ttu-id="33837-122">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="33837-122">For more information, see:</span></span>  
  
    -   [<span data-ttu-id="33837-123">Arbeiten mit Replikations-Agent-Profilen</span><span class="sxs-lookup"><span data-stu-id="33837-123">Work with Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
    -   [<span data-ttu-id="33837-124">Anzeigen und Ändern von Befehlszeilenparametern des Replikations-Agents &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="33837-124">View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;</span></span>](agents/view-and-modify-replication-agent-command-prompt-parameters.md)  
  
    -   <span data-ttu-id="33837-125">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md)zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="33837-125">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
2.  <span data-ttu-id="33837-126">Geben Sie die Beibehaltungsdauer für die Veröffentlichung so niedrig wie möglich an.</span><span class="sxs-lookup"><span data-stu-id="33837-126">Specify the lowest setting possible for the publication retention period.</span></span> <span data-ttu-id="33837-127">Weitere Informationen finden Sie unter [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="33837-127">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
3.  <span data-ttu-id="33837-128">Als Teil der Wartung für die Mergereplikation überprüfen Sie gelegentlich die Vergrößerung der Systemtabellen, die mit der Mergereplikation verbunden sind: **MSmerge_contents**, **MSmerge_genhistory**, **MSmerge_tombstone**, **MSmerge_current_partition_mappings**und **MSmerge_past_partition_mappings**.</span><span class="sxs-lookup"><span data-stu-id="33837-128">As part of maintenance for merge replication, occasionally check the growth of the system tables associated with merge replication: **MSmerge_contents**, **MSmerge_genhistory**, and **MSmerge_tombstone**, **MSmerge_current_partition_mappings**, and **MSmerge_past_partition_mappings**.</span></span> <span data-ttu-id="33837-129">Führen Sie eine regelmäßige Neuindizierung dieser Tabellen durch.</span><span class="sxs-lookup"><span data-stu-id="33837-129">Periodically re-index these tables.</span></span> <span data-ttu-id="33837-130">Weitere Informationen finden Sie unter [Neuorganisieren und Neuerstellen von Indizes](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="33837-130">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33837-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33837-131">See Also</span></span>  
 [<span data-ttu-id="33837-132">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="33837-132">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
