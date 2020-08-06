---
title: Anhalten und Fortsetzen der Datenbankspiegelung (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- sessions [SQL Server], database mirroring
- resuming database mirroring
- database mirroring [SQL Server], pausing
- database mirroring [SQL Server], resuming
- pausing database mirroring
ms.assetid: c67802c6-ee8c-4cbd-a6d4-f7b80413a4ab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8c231876b11303992e0e3300c9cb73c0cf53b3af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701858"
---
# <a name="pausing-and-resuming-database-mirroring-sql-server"></a><span data-ttu-id="c9734-102">Anhalten und Fortsetzen der Datenbankspiegelung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c9734-102">Pausing and Resuming Database Mirroring (SQL Server)</span></span>
  <span data-ttu-id="c9734-103">Der Datenbankbesitzer kann eine Datenbank-Spiegelungssitzung jederzeit anhalten und später fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="c9734-103">The database owner can pause and later resume a database mirroring session at any time.</span></span> <span data-ttu-id="c9734-104">Durch Anhalten bleibt der Sitzungsstatus erhalten, während die Spiegelung unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="c9734-104">Pausing preserves the session state while suspending mirroring.</span></span> <span data-ttu-id="c9734-105">Bei Engpässen ist das Anhalten möglicherweise nützlich, um die Leistung auf dem Prinzipalserver zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="c9734-105">During bottlenecks, pausing might be useful to improve performance on the principal server.</span></span>  
  
 <span data-ttu-id="c9734-106">Wenn eine Sitzung angehalten wird, bleibt die Prinzipaldatenbank weiterhin verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c9734-106">When a session is paused, the principal database remains available.</span></span> <span data-ttu-id="c9734-107">Durch das Anhalten wird der Status der Spiegelungssitzung auf SUSPENDED festgelegt, und die Spiegeldatenbank hält nicht mehr Schritt mit der Prinzipaldatenbank. Dadurch wird die Prinzipaldatenbank fehleranfällig ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c9734-107">Pausing sets the state of the mirroring session to SUSPENDED, and the mirror database no longer keeps up with the principal database, causing the principal database to run exposed.</span></span>  
  
 <span data-ttu-id="c9734-108">Es empfiehlt sich, eine angehaltene Sitzung rasch fortzusetzen, weil das Transaktionsprotokoll nicht gekürzt werden kann, während eine Datenbank-Spiegelungssitzung angehalten ist.</span><span class="sxs-lookup"><span data-stu-id="c9734-108">We recommend that you resume a paused session quickly, because as long as a database mirroring session remains paused, the transaction log cannot be truncated.</span></span> <span data-ttu-id="c9734-109">Wenn die Datenbank-Spiegelungssitzung zu lange angehalten wird, kann es somit sein, dass das Transaktionsprotokoll vollständig aufgefüllt wird und die Datenbank nicht mehr verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c9734-109">Therefore, if a database mirroring session is paused for too long, the transaction log fills up, making the database unavailable.</span></span> <span data-ttu-id="c9734-110">Eine Erläuterung dazu finden Sie unter "Auswirkung des Anhaltens und Fortsetzens auf die Protokollkürzung" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="c9734-110">For an explanation of why this happens, see "How Pausing and Resuming Affect Log Truncation," later in this topic.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c9734-111">Nach einem erzwungenen Dienst, wenn der ursprüngliche Prinzipalserver die Verbindung wiederherstellt, wird die Spiegelung angehalten.</span><span class="sxs-lookup"><span data-stu-id="c9734-111">Following a forced service, when the original principal server reconnects mirroring is suspended.</span></span> <span data-ttu-id="c9734-112">Das Fortsetzen der Spiegelung in dieser Situation könnte auf dem ursprünglichen Prinzipalserver zu Datenverlust führen.</span><span class="sxs-lookup"><span data-stu-id="c9734-112">Resuming mirroring in this situation could possibly cause data loss on the original principal server.</span></span> <span data-ttu-id="c9734-113">Weitere Informationen zum Verwalten des potenziellen Datenverlusts finden Sie unter [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="c9734-113">For information about managing the potential data loss, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
 <span data-ttu-id="c9734-114">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="c9734-114">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="c9734-115">Auswirkung des Anhaltens und Fortsetzens auf die Protokollkürzung</span><span class="sxs-lookup"><span data-stu-id="c9734-115">How Pausing and Resuming Affect Log Truncation</span></span>](#EffectOnLogTrunc)  
  
-   [<span data-ttu-id="c9734-116">Vermeiden eines vollen Transaktionsprotokolls</span><span class="sxs-lookup"><span data-stu-id="c9734-116">Avoid a Full Transaction Log</span></span>](#AvoidFullLog)  
  
-   [<span data-ttu-id="c9734-117">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="c9734-117">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="how-pausing-and-resuming-affect-log-truncation"></a><a name="EffectOnLogTrunc"></a> <span data-ttu-id="c9734-118">Auswirkung des Anhaltens und Fortsetzens auf die Protokollkürzung</span><span class="sxs-lookup"><span data-stu-id="c9734-118">How Pausing and Resuming Affect Log Truncation</span></span>  
 <span data-ttu-id="c9734-119">Wenn ein automatischer Prüfpunkt für eine Datenbank ausgeführt wird, wird normalerweise das zugehörige Transaktionsprotokoll nach der nächsten Protokollsicherung auf diesen Prüfpunkt gekürzt.</span><span class="sxs-lookup"><span data-stu-id="c9734-119">Normally, when an automatic checkpoint is performed on a database, its transaction log is truncated to that checkpoint after the next log backup.</span></span> <span data-ttu-id="c9734-120">Während eine Datenbank-Spiegelungssitzung angehalten ist, bleiben alle aktuellen Protokolldatensätze aktiv, weil der Prinzipalserver darauf wartet, sie an den Spiegelserver zu senden.</span><span class="sxs-lookup"><span data-stu-id="c9734-120">While a database mirroring session remains paused, all of the current log records remain active because the principal server is waiting to send them to the mirror server.</span></span> <span data-ttu-id="c9734-121">Die ungesendeten Protokolldatensätze sammeln sich im Transaktionsprotokoll der Prinzipaldatenbank an, bis die Sitzung fortgesetzt wird und der Prinzipalserver die Protokolldatensätze an den Spiegelserver gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="c9734-121">The unsent log records accumulate in the transaction log of the principal database until the session resumes and the principal server has sent the log records to the mirror server.</span></span>  
  
 <span data-ttu-id="c9734-122">Wenn die Sitzung fortgesetzt wird, beginnt der Prinzipalserver sofort damit, die akkumulierten Protokolldatensätze an den Spiegelserver zu senden.</span><span class="sxs-lookup"><span data-stu-id="c9734-122">When the session is resumed, the principal server immediately begins sending the accumulated log records to the mirror server.</span></span> <span data-ttu-id="c9734-123">Nachdem der Spiegelserver bestätigt hat, dass der dem ältesten automatischen Prüfpunkt entsprechende Protokolldatensatz in die Warteschlange gestellt wurde, kürzt der Prinzipalserver das Protokoll der Prinzipaldatenbank auf diesen Prüfpunkt.</span><span class="sxs-lookup"><span data-stu-id="c9734-123">After the mirror server confirms that it has queued the log record corresponding to the oldest automatic checkpoint, the principal server truncates the log of the principal database to that checkpoint.</span></span> <span data-ttu-id="c9734-124">Der Spiegelserver kürzt die Wiederholungswarteschlange auf denselben Protokolldatensatz.</span><span class="sxs-lookup"><span data-stu-id="c9734-124">The mirror server truncates the redo queue at the same log record.</span></span> <span data-ttu-id="c9734-125">Da dieser Prozess für jeden sukzessiven Prüfpunkt wiederholt wird, wird das Protokoll schrittweise, von Prüfpunkt zu Prüfpunkt, gekürzt.</span><span class="sxs-lookup"><span data-stu-id="c9734-125">As this process is repeated for each successive checkpoint, the log is truncated in stages, checkpoint by checkpoint.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9734-126">Weitere Informationen zu Prüfpunkten und der Protokollkürzung finden Sie unter [Datenbankprüfpunkte &#40;SQL Server&#41;](../../relational-databases/logs/database-checkpoints-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c9734-126">For more information about the checkpoints and log truncation, see [Database Checkpoints &#40;SQL Server&#41;](../../relational-databases/logs/database-checkpoints-sql-server.md).</span></span>  
  
##  <a name="avoid-a-full-transaction-log"></a><a name="AvoidFullLog"></a> <span data-ttu-id="c9734-127">Vermeiden eines vollen Transaktionsprotokolls</span><span class="sxs-lookup"><span data-stu-id="c9734-127">Avoid a Full Transaction Log</span></span>  
 <span data-ttu-id="c9734-128">Wenn das Protokoll voll ist (weil die maximale Größe erreicht wurde oder weil für die Serverinstanz der Speicherplatz nicht ausreicht), kann die Datenbank keine Updates mehr ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9734-128">If the log fills up (either because it reaches its maximum size or the server instance runs out of space), the database cannot perform any more updates.</span></span> <span data-ttu-id="c9734-129">Es gibt zwei Möglichkeiten, um dieses Problem zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="c9734-129">To avoid this problem, you have two alternatives:</span></span>  
  
-   <span data-ttu-id="c9734-130">Setzen Sie die Datenbank-Spiegelungssitzung fort, bevor das Protokoll voll ist, oder fügen Sie mehr Protokollspeicher hinzu.</span><span class="sxs-lookup"><span data-stu-id="c9734-130">Resume the database mirroring session before the log fills up, or add more log space.</span></span> <span data-ttu-id="c9734-131">Durch das Fortsetzen der Datenbankspiegelung kann der Prinzipalserver das angesammelte aktive Protokoll an den Spiegelserver senden, und die Spiegeldatenbank erhält den Status SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="c9734-131">Resuming database mirroring lets the principal server send its accumulated active log to the mirror server and puts the mirror database in the SYNCHRONIZING state.</span></span> <span data-ttu-id="c9734-132">Der Spiegelserver kann dann das Protokoll auf den Datenträger schreiben und damit beginnen, es zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="c9734-132">The mirror server can then harden the log to disk and start to redo it.</span></span>  
  
-   <span data-ttu-id="c9734-133">Beenden Sie die Datenbank-Spiegelungssitzung durch Entfernen der Spiegelung.</span><span class="sxs-lookup"><span data-stu-id="c9734-133">Stop the database mirroring session by removing mirroring.</span></span>  
  
     <span data-ttu-id="c9734-134">Im Gegensatz zum Anhalten einer Sitzung werden beim Entfernen der Spiegelung alle Informationen zur Spiegelungssitzung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c9734-134">Unlike pausing a session, removing mirroring drops all information about the mirroring session.</span></span> <span data-ttu-id="c9734-135">Jede Partnerserverinstanz behält eine eigene Kopie der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c9734-135">Each partner server instance retains its own copy of the database.</span></span> <span data-ttu-id="c9734-136">Wenn die frühere Spiegelkopie wiederhergestellt wird, weicht sie von der früheren Prinzipalkopie ab und liegt um die Zeitspanne zurück, die seit dem Anhalten der Sitzung vergangen ist.</span><span class="sxs-lookup"><span data-stu-id="c9734-136">If the former mirror copy is recovered, it will have diverged from the former principal copy and be behind by the amount of time that has elapsed since the session was paused.</span></span> <span data-ttu-id="c9734-137">Weitere Informationen finden Sie unter [Entfernen der Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c9734-137">For more information, see [Removing Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="c9734-138">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="c9734-138">Related Tasks</span></span>  
 <span data-ttu-id="c9734-139">**So halten Sie eine Datenbankspiegelung an bzw. setzen sie fort**</span><span class="sxs-lookup"><span data-stu-id="c9734-139">**To pause or resume database mirroring**</span></span>  
  
-   [<span data-ttu-id="c9734-140">Anhalten oder Fortsetzen einer Datenbank-Spiegelungssitzung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c9734-140">Pause or Resume a Database Mirroring Session &#40;SQL Server&#41;</span></span>](pause-or-resume-a-database-mirroring-session-sql-server.md)  
  
 <span data-ttu-id="c9734-141">**So beenden Sie die Datenbankspiegelung**</span><span class="sxs-lookup"><span data-stu-id="c9734-141">**To stop database mirroring**</span></span>  
  
-   [<span data-ttu-id="c9734-142">Entfernen der Datenbankspiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c9734-142">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](remove-database-mirroring-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="c9734-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9734-143">See Also</span></span>  
 <span data-ttu-id="c9734-144">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9734-144">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="c9734-145">[Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c9734-145">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="c9734-146">Entfernen der Datenbankspiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c9734-146">Removing Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  