---
title: MSSQLSERVER_14421 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 14421 (Database Engine error)
ms.assetid: 03e76d4a-d463-4673-8843-08e4ecaefe27
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d6bc793911797c334d87238ec46531f7afbf63ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620955"
---
# <a name="mssqlserver_14421"></a><span data-ttu-id="6cf8b-102">MSSQLSERVER_14421</span><span class="sxs-lookup"><span data-stu-id="6cf8b-102">MSSQLSERVER_14421</span></span>
    
## <a name="details"></a><span data-ttu-id="6cf8b-103">Details</span><span class="sxs-lookup"><span data-stu-id="6cf8b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6cf8b-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="6cf8b-104">Product Name</span></span>|<span data-ttu-id="6cf8b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6cf8b-105">SQL Server</span></span>|  
|<span data-ttu-id="6cf8b-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="6cf8b-106">Event ID</span></span>|<span data-ttu-id="6cf8b-107">14421</span><span class="sxs-lookup"><span data-stu-id="6cf8b-107">14421</span></span>|  
|<span data-ttu-id="6cf8b-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="6cf8b-108">Event Source</span></span>|<span data-ttu-id="6cf8b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6cf8b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6cf8b-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="6cf8b-110">Component</span></span>|<span data-ttu-id="6cf8b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6cf8b-111">SQLEngine</span></span>|  
|<span data-ttu-id="6cf8b-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="6cf8b-112">Symbolic Name</span></span>|<span data-ttu-id="6cf8b-113">SQLErrorNum14421</span><span class="sxs-lookup"><span data-stu-id="6cf8b-113">SQLErrorNum14421</span></span>|  
|<span data-ttu-id="6cf8b-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="6cf8b-114">Message Text</span></span>|<span data-ttu-id="6cf8b-115">Die sekundäre Datenbank für den Protokollversand, %s.%s, weist eine Wiederherstellungsschwelle von %d Minuten auf und ist nicht mehr synchronisiert. Während %d Minuten wurde keine Wiederherstellung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-115">The log shipping secondary database %s.%s has restore threshold of %d minutes and is out of sync. No restore was performed for %d minutes.</span></span> <span data-ttu-id="6cf8b-116">Die Wiederherstellungslatenzzeit beträgt %d Minuten.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-116">Restored latency is %d minutes.</span></span> <span data-ttu-id="6cf8b-117">Überprüfen Sie das Agentprotokoll und die Informationen des Protokollversandmonitors.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-117">Check agent log and logshipping monitor information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6cf8b-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="6cf8b-118">Explanation</span></span>  
 <span data-ttu-id="6cf8b-119">Mit dieser Meldung wird angegeben, dass der Protokollversand außerhalb der Wiederherstellungsschwelle nicht mehr synchronisiert ist.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-119">This message indicates that log shipping is out of synchronization beyond the restore threshold.</span></span> <span data-ttu-id="6cf8b-120">Bei der Wiederherstellungsschwelle handelt es sich um eine Zeit in Minuten, die zwischen den Wiederherstellungsvorgängen vergehen kann, bevor eine Meldung erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-120">The restore threshold is the number of minutes that can elapse between restore operations before a message is generated.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="6cf8b-121">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="6cf8b-121">Possible Causes</span></span>  
 <span data-ttu-id="6cf8b-122">Mit dieser Meldung wird nicht unbedingt ein Problem beim Protokollversand angegeben.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-122">This message does not necessarily indicate a problem with log shipping.</span></span> <span data-ttu-id="6cf8b-123">Stattdessen wird mit dieser Meldung eines der folgenden Probleme angegeben:</span><span class="sxs-lookup"><span data-stu-id="6cf8b-123">Instead, this message might indicate one of the following problems:</span></span>  
  
-   <span data-ttu-id="6cf8b-124">Der Wiederherstellungsauftrag wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-124">The restore job is not running.</span></span>  
  
     <span data-ttu-id="6cf8b-125">Folgende mögliche Ursachen können vorliegen, dass der Auftrag nicht ausgeführt wird: Der SQL Server-Agent-Dienst in der sekundären Serverinstanz wird nicht ausgeführt, der Auftrag wurde deaktiviert, oder der Zeitplan für den Auftrag wurde geändert.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-125">Possible causes of the job not running include the following: the SQL Server Agent service on the secondary server instance is not running, the job is disabled, or the schedule of the job has been changed.</span></span>  
  
-   <span data-ttu-id="6cf8b-126">Fehler beim Wiederherstellungsauftrag.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-126">The restore job is failing.</span></span>  
  
     <span data-ttu-id="6cf8b-127">Folgende mögliche Ursachen können für den Fehler beim Auftrag vorliegen: Der Pfad des Wiederherstellungsordners ist nicht gültig, der Datenträger ist voll, oder es liegt ein anderer Grund vor, wonach ein Fehler bei der RESTORE-Anweisung auftritt.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-127">Possible causes of the job failing include the following: the restore folder path is not valid, the disk is full, or any other reason that the RESTORE statement could fail.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6cf8b-128">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="6cf8b-128">User Action</span></span>  
 <span data-ttu-id="6cf8b-129">So beheben Sie das mit dieser Meldung angegebene Problem:</span><span class="sxs-lookup"><span data-stu-id="6cf8b-129">To troubleshoot this message:</span></span>  
  
-   <span data-ttu-id="6cf8b-130">Stellen Sie sicher, dass der SQL Server-Agent-Dienst in der sekundären Serverinstanz ausgeführt wird, dass der Wiederherstellungsauftrag für diese sekundäre Datenbank aktiviert ist und dass er so geplant ist, dass er in der entsprechenden Häufigkeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-130">Make sure that the SQL Server Agent service is running for the secondary server instance and that the restore job for this secondary database is enabled and is scheduled to run at the appropriate frequency.</span></span>  
  
-   <span data-ttu-id="6cf8b-131">Möglicherweise tritt beim Wiederherstellungsauftrag auf dem sekundären Server ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-131">The restore job on the secondary server might be failing.</span></span> <span data-ttu-id="6cf8b-132">Überprüfen Sie in diesem Fall den Auftragsverlauf für den Wiederherstellungsauftrag, und suchen Sie nach der Ursache.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-132">In this case, check the job history for the restore job to look for the cause.</span></span>  
  
-   <span data-ttu-id="6cf8b-133">Für den in der sekundären Serverinstanz ausgeführten Wiederherstellungsauftrag des Protokollversands kann möglicherweise keine Verbindung mit der Überwachungsserverinstanz hergestellt werden, um die **log_shipping_monitor_secondary**-Tabelle zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-133">The log shipping restore job, which runs on the secondary server instance, might not be able to connect to the monitor server instance to update the **log_shipping_monitor_secondary** table.</span></span> <span data-ttu-id="6cf8b-134">Dies beruht möglicherweise auf einem Authentifizierungsproblem zwischen der Überwachungsserverinstanz und der sekundären Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-134">This might be caused by an authentication problem between the monitor server instance and the secondary server instance.</span></span>  
  
-   <span data-ttu-id="6cf8b-135">Die Sicherungswarnschwelle weist möglicherweise einen falschen Wert auf.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-135">The backup alert threshold might have an incorrect value.</span></span> <span data-ttu-id="6cf8b-136">Im Idealfall ist dieser Wert auf den dreifachen Wert der Häufigkeit festgelegt, mit der der Wiederherstellungsauftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-136">Ideally, this value is set to at least three times the frequency of the restore job.</span></span> <span data-ttu-id="6cf8b-137">Wenn Sie die Häufigkeit für den Wiederherstellungsauftrag ändern, nachdem der Protokollversand konfiguriert und ausgeführt wurde, müssen Sie den Wert für die Sicherungswarnschwelle entsprechend aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-137">If you change the frequency of the restore job after log shipping is configured and functional, you must update the value of the backup alert threshold accordingly.</span></span>  
  
-   <span data-ttu-id="6cf8b-138">Wenn die Überwachungsserverinstanz offline geschaltet und anschließend wieder online geschaltet wird, wird die **log_shipping_monitor_secondary**-Tabelle erst dann mit den aktuellen Werten aktualisiert, wenn der Warnmeldungsauftrag ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-138">When the monitor server instance goes offline and then comes back online, the **log_shipping_monitor_secondary** table is not updated with the current values before the alert message job runs.</span></span> <span data-ttu-id="6cf8b-139">Der Fehler 14421 kann ausgelöst werden, wenn ein Wiederherstellungsauftrag mit folgender Meldung erfolgreich ausgeführt wurde: "Für die sekundäre Datenbank wurde keine anwendbare Protokollsicherungsdatei gefunden."</span><span class="sxs-lookup"><span data-stu-id="6cf8b-139">Error 14421 can be raised when a restore job succeeds with, "Could not find a log backup file that could be applied to secondary database."</span></span> <span data-ttu-id="6cf8b-140">Wenn dieser Fehler auftritt, wird der Speicherzeitpunkt nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-140">When this occurs, the restore time is not updated.</span></span> <span data-ttu-id="6cf8b-141">Möglicherweise beruht der Fehler in diesem Fall auf einem Problem mit dem Kopierauftrag.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-141">The cause of the error in this case might be an issue with the copy job.</span></span>  
  
     <span data-ttu-id="6cf8b-142">Wenn Sie die Überwachungstabellen mit den neuesten Daten für die sekundäre Datenbank aktualisieren möchten, führen Sie **sp_refresh_log_shipping_monitor** in der sekundären Serverinstanz aus.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-142">To update the monitor tables with the latest data for the secondary database, run **sp_refresh_log_shipping_monitor** on the secondary server instance.</span></span>  
  
-   <span data-ttu-id="6cf8b-143">Das Datum oder die Uhrzeit in der sekundären Serverinstanz oder in der Überwachungsserverinstanz ist nicht richtig.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-143">On the secondary or monitor server instance, the date or time is incorrect.</span></span> <span data-ttu-id="6cf8b-144">Dadurch werden möglicherweise Warnmeldungen generiert.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-144">This may also generate alert messages.</span></span> <span data-ttu-id="6cf8b-145">Möglicherweise wurde das Systemdatum oder die Systemuhrzeit für eine der Instanzen geändert.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-145">Possibly the system date or time was modified on the one of them.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6cf8b-146">Unterschiedliche Zeitzonen für die beiden Serverinstanzen sollten kein Problem darstellen.</span><span class="sxs-lookup"><span data-stu-id="6cf8b-146">Different time zones for the two server instances should not cause a problem.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cf8b-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6cf8b-147">See Also</span></span>  
 <span data-ttu-id="6cf8b-148">[log_shipping_monitor_secondary &#40;Transact-SQL-&#41;](/sql/relational-databases/system-tables/log-shipping-monitor-secondary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6cf8b-148">[log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/log-shipping-monitor-secondary-transact-sql) </span></span>  
 <span data-ttu-id="6cf8b-149">[Informationen zum Protokollversand &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6cf8b-149">[About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="6cf8b-150">[sp_help_log_shipping_monitor_secondary &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-secondary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6cf8b-150">[sp_help_log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-secondary-transact-sql) </span></span>  
 <span data-ttu-id="6cf8b-151">[sp_refresh_log_shipping_monitor &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6cf8b-151">[sp_refresh_log_shipping_monitor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span></span>  
 [<span data-ttu-id="6cf8b-152">Informationen zum Protokollversand &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6cf8b-152">About Log Shipping &#40;SQL Server&#41;</span></span>](../../database-engine/log-shipping/about-log-shipping-sql-server.md)  
  
  
