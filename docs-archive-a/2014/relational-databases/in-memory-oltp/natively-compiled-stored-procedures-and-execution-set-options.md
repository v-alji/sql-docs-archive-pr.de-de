---
title: Systemintern kompilierte gespeicherte Prozeduren und deren Ausführung mit SET-Optionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c1869cf7-9030-4d18-85d6-0e419a4e9af7
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 264a2b3ab1e6f3f0bda97bfe89a4438aa641577d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725750"
---
# <a name="natively-compiled-stored-procedures-and-execution-set-options"></a><span data-ttu-id="54da5-102">Systemintern kompilierte gespeicherte Prozeduren und deren Ausführung mit SET-Optionen</span><span class="sxs-lookup"><span data-stu-id="54da5-102">Natively Compiled Stored Procedures and Execution Set Options</span></span>
  <span data-ttu-id="54da5-103">Sitzungsoptionen sind in ATOMIC-Blöcken fest definiert.</span><span class="sxs-lookup"><span data-stu-id="54da5-103">Session options are fixed in atomic blocks.</span></span> <span data-ttu-id="54da5-104">Die Ausführung einer gespeicherten Prozedur wird durch die SET-Optionen einer Sitzung nicht beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="54da5-104">A stored procedure's execution is not affected by a session's SET options.</span></span> <span data-ttu-id="54da5-105">Bestimmte SET-Optionen, wie SET NOEXEC und SET SHOWPLAN_XML, bewirken jedoch, dass gespeicherte Prozeduren (einschließlich systemintern kompilierter gespeicherter Prozeduren) nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="54da5-105">However, certain SET options, such as SET NOEXEC and SET SHOWPLAN_XML, cause stored procedures (including natively compiled stored procedures) to not execute.</span></span>  
  
 <span data-ttu-id="54da5-106">Wenn eine systemintern kompilierte gespeicherte Prozedur mit einer aktivierten STATISTICS-Option ausgeführt wird, werden Statistiken für die Prozedur als Ganzes und nicht pro Anweisung erfasst.</span><span class="sxs-lookup"><span data-stu-id="54da5-106">When a natively compiled stored procedure is executed with any STATISTICS option turned on, statistics are gathered for the procedure as a whole and not per statement.</span></span> <span data-ttu-id="54da5-107">Weitere Informationen finden Sie unter [SET STATISTICS IO &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-io-transact-sql), [SET STATISTICS PROFILE &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-profile-transact-sql), [SET STATISTICS TIME &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-time-transact-sql) und [SET STATISTICS XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-xml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54da5-107">For more information, see [SET STATISTICS IO &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-io-transact-sql), [SET STATISTICS PROFILE &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-profile-transact-sql), [SET STATISTICS TIME &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-time-transact-sql), and [SET STATISTICS XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-xml-transact-sql).</span></span> <span data-ttu-id="54da5-108">Um für systemintern gespeicherte Prozeduren eine Ausführungsstatistik pro Anweisung abzurufen, verwenden Sie für das sp_statement_completed-Ereignis eine Sitzung für erweiterte Ereignisse. Diese startet, nachdem alle Abfragen in der Ausführung einer gespeicherten Prozedur abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="54da5-108">To obtain execution statistics on a per-statement level in natively compiled stored procedures, use an Extended Event session on the sp_statement_completed event, which starts when each individual query in a stored procedures execution completes.</span></span> <span data-ttu-id="54da5-109">Weitere Informationen zum Erstellen einer Sitzung für erweiterte Ereignisse finden Sie unter [CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54da5-109">For more information on creating Extended Event sessions, see [CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql).</span></span>  
  
 <span data-ttu-id="54da5-110">`SHOWPLAN_XML` wird für systemintern kompilierte gespeicherte Prozeduren unterstützt.</span><span class="sxs-lookup"><span data-stu-id="54da5-110">`SHOWPLAN_XML` is supported for natively compiled stored procedures.</span></span> <span data-ttu-id="54da5-111">`SHOWPLAN_ALL` und `SHOWPLAN_TEXT` werden bei systemintern kompilierten gespeicherten Prozeduren nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="54da5-111">`SHOWPLAN_ALL` and `SHOWPLAN_TEXT` are not supported with natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="54da5-112">`SET FMTONLY` wird bei systemintern kompilierten gespeicherten Prozeduren nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="54da5-112">`SET FMTONLY` in not supported with natively compiled stored procedures.</span></span> <span data-ttu-id="54da5-113">Verwenden Sie stattdessen [sp_describe_first_result_set &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-describe-first-result-set-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54da5-113">Use [sp_describe_first_result_set &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-describe-first-result-set-transact-sql) instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54da5-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54da5-114">See Also</span></span>  
 [<span data-ttu-id="54da5-115">Nativ kompilierte gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="54da5-115">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
