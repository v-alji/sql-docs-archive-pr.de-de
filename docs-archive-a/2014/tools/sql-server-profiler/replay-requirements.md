---
title: Wiedergabe Anforderungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event classes [SQL Server], replaying traces
- traces [SQL Server], replaying
- replaying traces
- TSQL_Replay template [SQL Server]
ms.assetid: 0e01dfc7-84b9-47f6-8bf7-b0656df4fa7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 65546f6820765286b558d2043e0155a79a07eb58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722054"
---
# <a name="replay-requirements"></a><span data-ttu-id="4bf28-102">Replay Requirements</span><span class="sxs-lookup"><span data-stu-id="4bf28-102">Replay Requirements</span></span>
  <span data-ttu-id="4bf28-103">Um Ablaufverfolgungsdaten mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] oder dem Distributed Replay Utility wiedergeben zu können, müssen in der Ablaufverfolgung bestimmte Ereignisklassen und Spalten aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="4bf28-103">In order to replay trace data with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or the Distributed Replay Utility, a specific set of event classes and columns must be captured in the trace.</span></span> <span data-ttu-id="4bf28-104">Diese Einstellungen sind standardmäßig aktiviert, wenn mit der **TSQL_Replay** -Ablaufverfolgungsvorlage eine Ablaufverfolgung konfiguriert wird, die später zur Wiedergabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4bf28-104">These settings are enabled by default if the **TSQL_Replay** trace template is used to configure a trace that is later used for replay.</span></span> <span data-ttu-id="4bf28-105">In diesem Thema sind diese Einstellungen und weiteren Wiedergabeanforderungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4bf28-105">This topic describes these settings and other replay requirements.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4bf28-106">Es empfiehlt sich, zum Wiedergeben einer intensiven OLTP-Anwendung das Distributed Replay Utility (mit zahlreichen aktiven gleichzeitigen Verbindungen oder hohem Durchsatz) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4bf28-106">We recommend using the Distributed Replay Utility for replaying an intensive OLTP application (with many active concurrent connections or high throughput).</span></span> <span data-ttu-id="4bf28-107">Mit dem Distributed Replay Utility können Sie Ablaufverfolgungsdaten von mehreren Computern wiedergeben, um unternehmenswichtige Arbeitsauslastungen besser zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="4bf28-107">The Distributed Replay Utility can replay trace data from multiple computers, better simulating a mission-critical workload.</span></span> <span data-ttu-id="4bf28-108">Weitere Informationen finden Sie unter [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="4bf28-108">For more information, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
## <a name="event-classes-required-for-replay"></a><span data-ttu-id="4bf28-109">Für die Wiedergabe erforderliche Ereignisklassen</span><span class="sxs-lookup"><span data-stu-id="4bf28-109">Event Classes Required for Replay</span></span>  
 <span data-ttu-id="4bf28-110">Für die Wiedergabe durch [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]müssen neben allen anderen zu überwachenden Ereignisklassen die folgenden Ereignisklassen in der Ablaufverfolgung aufgezeichnet werden:</span><span class="sxs-lookup"><span data-stu-id="4bf28-110">To be replayed by [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], the following set of event classes, in addition to any other event classes you want to monitor, must be captured in the trace:</span></span>  
  
-   <span data-ttu-id="4bf28-111">**CursorClose**(nur beim Wiedergeben serverseitiger Cursor)</span><span class="sxs-lookup"><span data-stu-id="4bf28-111">**CursorClose (** only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="4bf28-112">**CursorExecute** (nur beim Wiedergeben serverseitiger Cursor)</span><span class="sxs-lookup"><span data-stu-id="4bf28-112">**CursorExecute** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="4bf28-113">**CursorOpen** (nur beim Wiedergeben serverseitiger Cursor)</span><span class="sxs-lookup"><span data-stu-id="4bf28-113">**CursorOpen** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="4bf28-114">**CursorPrepare** (nur beim Wiedergeben serverseitiger Cursor)</span><span class="sxs-lookup"><span data-stu-id="4bf28-114">**CursorPrepare** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="4bf28-115">**CursorUnprepare** (nur beim Wiedergeben serverseitiger Cursor)</span><span class="sxs-lookup"><span data-stu-id="4bf28-115">**CursorUnprepare** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="4bf28-116">**Audit Login**</span><span class="sxs-lookup"><span data-stu-id="4bf28-116">**Audit Login**</span></span>  
  
-   <span data-ttu-id="4bf28-117">**Audit Logout**</span><span class="sxs-lookup"><span data-stu-id="4bf28-117">**Audit Logout**</span></span>  
  
-   <span data-ttu-id="4bf28-118">**ExistingConnection**</span><span class="sxs-lookup"><span data-stu-id="4bf28-118">**ExistingConnection**</span></span>  
  
-   <span data-ttu-id="4bf28-119">**RPC Output Parameter**</span><span class="sxs-lookup"><span data-stu-id="4bf28-119">**RPC Output Parameter**</span></span>  
  
-   <span data-ttu-id="4bf28-120">**RPC:Completed**</span><span class="sxs-lookup"><span data-stu-id="4bf28-120">**RPC:Completed**</span></span>  
  
-   <span data-ttu-id="4bf28-121">**RPC:Starting**</span><span class="sxs-lookup"><span data-stu-id="4bf28-121">**RPC:Starting**</span></span>  
  
-   <span data-ttu-id="4bf28-122">**Exec Prepared SQL** (nur beim Wiedergeben serverseitig vorbereiteter SQL-Anweisungen)</span><span class="sxs-lookup"><span data-stu-id="4bf28-122">**Exec Prepared SQL** (only required when replaying server-side prepared SQL statements)</span></span>  
  
-   <span data-ttu-id="4bf28-123">**Prepare SQL** (nur beim Wiedergeben serverseitig vorbereiteter SQL-Anweisungen)</span><span class="sxs-lookup"><span data-stu-id="4bf28-123">**Prepare SQL** (only required when replaying server-side prepared SQL statements)</span></span>  
  
-   <span data-ttu-id="4bf28-124">**SQL:BatchCompleted**</span><span class="sxs-lookup"><span data-stu-id="4bf28-124">**SQL:BatchCompleted**</span></span>  
  
-   <span data-ttu-id="4bf28-125">**SQL:BatchStarting**</span><span class="sxs-lookup"><span data-stu-id="4bf28-125">**SQL:BatchStarting**</span></span>  
  
## <a name="data-columns-required-for-replay"></a><span data-ttu-id="4bf28-126">Für die Wiedergabe erforderliche Datenspalten</span><span class="sxs-lookup"><span data-stu-id="4bf28-126">Data Columns Required for Replay</span></span>  
 <span data-ttu-id="4bf28-127">Zusätzlich zu anderen Datenspalten, die Sie aufzeichnen möchten, müssen die folgenden Datenspalten in einer Ablaufverfolgung aufgezeichnet sein, damit die Ablaufverfolgung wiedergegeben werden kann:</span><span class="sxs-lookup"><span data-stu-id="4bf28-127">In addition to any other data columns you want to capture, the following data columns must be captured in a trace to allow the trace to be replayed:</span></span>  
  
-   <span data-ttu-id="4bf28-128">**Ereignisklasse**</span><span class="sxs-lookup"><span data-stu-id="4bf28-128">**Event Class**</span></span>  
  
-   <span data-ttu-id="4bf28-129">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="4bf28-129">**EventSequence**</span></span>  
  
-   <span data-ttu-id="4bf28-130">**TextData**</span><span class="sxs-lookup"><span data-stu-id="4bf28-130">**TextData**</span></span>  
  
-   <span data-ttu-id="4bf28-131">**Anwendungsname**</span><span class="sxs-lookup"><span data-stu-id="4bf28-131">**Application Name**</span></span>  
  
-   <span data-ttu-id="4bf28-132">**LoginName**</span><span class="sxs-lookup"><span data-stu-id="4bf28-132">**LoginName**</span></span>  
  
-   <span data-ttu-id="4bf28-133">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="4bf28-133">**DatabaseName**</span></span>  
  
-   <span data-ttu-id="4bf28-134">**Datenbank-ID**</span><span class="sxs-lookup"><span data-stu-id="4bf28-134">**Database ID**</span></span>  
  
-   <span data-ttu-id="4bf28-135">**ClientProcessID**</span><span class="sxs-lookup"><span data-stu-id="4bf28-135">**ClientProcessID**</span></span>  
  
-   <span data-ttu-id="4bf28-136">**HostName**</span><span class="sxs-lookup"><span data-stu-id="4bf28-136">**HostName**</span></span>  
  
-   <span data-ttu-id="4bf28-137">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="4bf28-137">**ServerName**</span></span>  
  
-   <span data-ttu-id="4bf28-138">**Binärdaten**</span><span class="sxs-lookup"><span data-stu-id="4bf28-138">**Binary Data**</span></span>  
  
-   <span data-ttu-id="4bf28-139">**SPID**</span><span class="sxs-lookup"><span data-stu-id="4bf28-139">**SPID**</span></span>  
  
-   <span data-ttu-id="4bf28-140">**Startzeit**</span><span class="sxs-lookup"><span data-stu-id="4bf28-140">**Start Time**</span></span>  
  
-   <span data-ttu-id="4bf28-141">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="4bf28-141">**EndTime**</span></span>  
  
-   <span data-ttu-id="4bf28-142">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="4bf28-142">**IsSystem**</span></span>  
  
-   <span data-ttu-id="4bf28-143">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="4bf28-143">**NTDomainName**</span></span>  
  
-   <span data-ttu-id="4bf28-144">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="4bf28-144">**NTUserName**</span></span>  
  
-   <span data-ttu-id="4bf28-145">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="4bf28-145">**Error**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4bf28-146">Mithilfe der Ablaufverfolgungsvorlage **TSQL_Replay** können Sie Ablaufverfolgungen erstellen, die Daten für die Wiedergabe aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="4bf28-146">Use the trace template **TSQL_Replay** for traces that capture data for replay.</span></span>  
  
## <a name="other-replay-requirements"></a><span data-ttu-id="4bf28-147">Weitere Anforderungen für die Wiedergabe</span><span class="sxs-lookup"><span data-stu-id="4bf28-147">Other Replay Requirements</span></span>  
 <span data-ttu-id="4bf28-148">In Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]wird durch die Wiedergabe überprüft, ob die benötigten Ereignisse und Spalten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="4bf28-148">In Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], replay checks for the presence of required events and columns.</span></span> <span data-ttu-id="4bf28-149">Durch diese Änderung wird nicht nur die Genauigkeit der Wiedergabe erhöht, sondern auch die Suche bei der Problembehandlung vereinfacht, insbesondere wenn benötigte Daten fehlen.</span><span class="sxs-lookup"><span data-stu-id="4bf28-149">This change helps improve the accuracy of replay and takes the guesswork out of troubleshooting replay when required data is missing.</span></span> <span data-ttu-id="4bf28-150">Die Wiedergabe gibt einen Fehler zurück und hält die Wiedergabe der aktuellen Datei an, wenn die von der Ablaufverfolgung benötigten Daten fehlen.</span><span class="sxs-lookup"><span data-stu-id="4bf28-150">Replay returns an error and stops replaying a file when required data is missing from a trace.</span></span>  
  
 <span data-ttu-id="4bf28-151">Wenn Sie eine Ablaufverfolgung für einen Server mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (das Ziel) wiedergeben möchten und dieser Server nicht mit dem Server übereinstimmt, für den die Ablaufverfolgung ursprünglich erstellt wurde, sollten folgende Schritte ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="4bf28-151">To replay a trace against a server (the target) on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running other than the server originally traced (the source), make sure the following has been done:</span></span>  
  
-   <span data-ttu-id="4bf28-152">Alle in der Ablaufverfolgung enthaltenen Benutzernamen und Benutzer müssen bereits auf dem Ziel und in derselben Datenbank wie auf der Quelle erstellt worden sein.</span><span class="sxs-lookup"><span data-stu-id="4bf28-152">All logins and users contained in the trace must be created already on the target and in the same database as the source.</span></span>  
  
-   <span data-ttu-id="4bf28-153">Alle Benutzernamen und Benutzer auf dem Ziel müssen über dieselben Berechtigungen wie auf der Quelle verfügen.</span><span class="sxs-lookup"><span data-stu-id="4bf28-153">All logins and users in the target must have the same permissions they had in the source.</span></span>  
  
-   <span data-ttu-id="4bf28-154">Alle Anmeldekennwörter müssen mit den Kennwörtern des Benutzers übereinstimmen, der die Wiedergabe ausführt.</span><span class="sxs-lookup"><span data-stu-id="4bf28-154">All login passwords must be the same as those of the user that executes the replay.</span></span>  
  
-   <span data-ttu-id="4bf28-155">Die Datenbank-IDs auf dem Ziel sollten mit denen auf der Quelle übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="4bf28-155">The database IDs on the target ideally should be the same as those on the source.</span></span> <span data-ttu-id="4bf28-156">Andernfalls können Sie basierend auf **DatabaseName** einen Abgleich ausführen, sofern dieser in der Ablaufverfolgung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="4bf28-156">However, if they are not the same, matching can be performed based on **DatabaseName** if it is present in the trace.</span></span>  
  
-   <span data-ttu-id="4bf28-157">Die Standarddatenbank für jeden in der Ablaufverfolgung enthaltenen Benutzernamen muss (auf dem Ziel) auf die entsprechende Zieldatenbank des Benutzernamens festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4bf28-157">The default database for each login contained in the trace must be set (on the target) to the respective target database of the login.</span></span> <span data-ttu-id="4bf28-158">Beispielsweise enthält die wiederzugebende Ablaufverfolgung Aktivitäten für den Benutzernamen **Fred**in der **Fred_Db** -Datenbank der Quelle.</span><span class="sxs-lookup"><span data-stu-id="4bf28-158">For example, the trace to be replayed contains activity for the login, **Fred**, in the database **Fred_Db** on the source.</span></span> <span data-ttu-id="4bf28-159">Daher muss die Standarddatenbank auf dem Ziel für den Benutzernamen **Fred**auf die Datenbank festgelegt werden, die mit **Fred_Db** übereinstimmt (selbst wenn sich der Datenbankname unterscheidet).</span><span class="sxs-lookup"><span data-stu-id="4bf28-159">Therefore, on the target, the default database for the login, **Fred**, must be set to the database that matches **Fred_Db** (even if the database name is different).</span></span> <span data-ttu-id="4bf28-160">Legen Sie mithilfe der gespeicherten Systemprozedur **sp_defaultdb** die Standarddatenbank für den Benutzernamen fest.</span><span class="sxs-lookup"><span data-stu-id="4bf28-160">To set the default database of the login, use the **sp_defaultdb** system stored procedure.</span></span>  
  
 <span data-ttu-id="4bf28-161">Beim Wiedergeben von Ereignissen, die fehlende oder fehlerhafte Benutzernamen aufweisen, können Wiedergabefehler auftreten, die Wiedergabe wird jedoch fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4bf28-161">Replaying events associated with missing or incorrect logins results in replay errors, but the replay operation continues.</span></span>  
  
 <span data-ttu-id="4bf28-162">Informationen zu den Berechtigungen, die zum Wiedergeben einer Ablaufverfolgung erforderlich sind, finden Sie unter [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="4bf28-162">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf28-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4bf28-163">See Also</span></span>  
 <span data-ttu-id="4bf28-164">[Wiedergeben einer Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4bf28-164">[Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4bf28-165">[Wiedergeben einer Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4bf28-165">[Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4bf28-166">[Ereignisklassen in SQL Server: Referenz](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4bf28-166">[SQL Server Event Class Reference](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span></span>  
 <span data-ttu-id="4bf28-167">[sp_defaultdb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4bf28-167">[sp_defaultdb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql) </span></span>  
 [<span data-ttu-id="4bf28-168">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="4bf28-168">SQL Server Distributed Replay</span></span>](../distributed-replay/sql-server-distributed-replay.md)  
  
  
