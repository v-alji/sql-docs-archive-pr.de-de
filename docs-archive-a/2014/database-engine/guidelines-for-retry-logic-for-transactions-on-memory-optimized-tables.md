---
title: Richtlinien für Wiederholungs Logik für Transaktionen in Speicher optimierten Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f2a35c37-4449-49ee-8bba-928028f1de66
author: stevestein
ms.author: sstein
ms.openlocfilehash: c9ffaccefb8d4e0a3044c4858a06029fd4350354
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701582"
---
# <a name="guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables"></a><span data-ttu-id="89871-102">Richtlinien zur Wiederholungslogik für Transaktionen auf speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="89871-102">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>
  <span data-ttu-id="89871-103">Es gibt Fehlerbedingungen, die bei Transaktionen auftreten, die auf speicheroptimierte Tabellen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="89871-103">There are error conditions that occur with transactions that access memory-optimized tables.</span></span>  
  
-   41302. <span data-ttu-id="89871-104">Die aktuelle Transaktion hat versucht, einen Datensatz zu aktualisieren, der seit dem Start dieser Transaktion aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="89871-104">The current transaction attempted to update a record that has been updated since the transaction started.</span></span>  
  
-   41305. <span data-ttu-id="89871-105">Fehler beim Ausführen eines Commits für die aktuelle Transaktion aufgrund eines REPEATABLE READ-Überprüfungsfehlers.</span><span class="sxs-lookup"><span data-stu-id="89871-105">The current transaction failed to commit due to a repeatable read validation failure.</span></span>  
  
-   41325. <span data-ttu-id="89871-106">Für die aktuelle Transaktion wurde aufgrund eines serialisierbaren Überprüfungsfehlers kein Commit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="89871-106">The current transaction failed to commit due to a serializable validation failure.</span></span>  
  
-   41301. <span data-ttu-id="89871-107">Eine vorherige Transaktion, zu der die aktuelle Transaktion eine Abhängigkeit eingegangen war, wurde abgebrochen. Die aktuelle Transaktion kann keinen Commit mehr ausführen.</span><span class="sxs-lookup"><span data-stu-id="89871-107">A previous transaction that the current transaction took a dependency on has aborted, and the current transaction can no longer commit.</span></span>  
  
 <span data-ttu-id="89871-108">Eine häufige Ursache für diesen Fehler ist die gegenseitige Beeinflussung von gleichzeitig ausgeführten Transaktion.</span><span class="sxs-lookup"><span data-stu-id="89871-108">A common cause of these errors is interference between concurrently executing transaction.</span></span> <span data-ttu-id="89871-109">Die gängige Korrekturmaßnahme besteht darin, die Transaktion zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="89871-109">The common corrective action is to retry the transaction.</span></span>  
  
 <span data-ttu-id="89871-110">Weitere Informationen zu diesen Fehlerbedingungen finden Sie im Abschnitt zu Konflikterkennung, Validierung und Commit-Abhängigkeits Prüfungen in [Transaktionen in Speicher optimierten Tabellen](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="89871-110">For more information about these error conditions, see the section on Conflict Detection, Validation, and Commit Dependency Checks in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="89871-111">Deadlocks (Fehlercode 1205) können bei speicheroptimierten Tabellen nicht auftreten.</span><span class="sxs-lookup"><span data-stu-id="89871-111">Deadlocks (error code 1205) cannot occur for memory-optimized tables.</span></span> <span data-ttu-id="89871-112">Sperren werden bei speicheroptimierten Tabellen nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="89871-112">Locks are not used for memory-optimized tables.</span></span> <span data-ttu-id="89871-113">Wenn die Anwendung allerdings bereits Wiederholungslogik für Deadlocks enthält, könnte die vorhandene Logik erweitert werden, um die neuen Fehlercodes einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="89871-113">However, if the application already contains retry logic for deadlocks, the existing logic could be extended to include the new error codes.</span></span>  
  
## <a name="considerations-for-retrying"></a><span data-ttu-id="89871-114">Überlegungen zu Wiederholungen</span><span class="sxs-lookup"><span data-stu-id="89871-114">Considerations for Retrying</span></span>  
 <span data-ttu-id="89871-115">Bei Anwendungen treten in der Regel Konflikte zwischen Transaktionen auf, und zur Behebung dieser Konflikte muss Wiederholungslogik implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="89871-115">Applications will typically encounter conflicts between transactions and need to implement retry logic to resolve those conflicts.</span></span> <span data-ttu-id="89871-116">Die Anzahl der aufgetretenen Konflikte hängt von mehreren Faktoren ab:</span><span class="sxs-lookup"><span data-stu-id="89871-116">The number of conflicts encountered depends on a number of factors:</span></span>  
  
-   <span data-ttu-id="89871-117">Konflikt bei einzelnen Zeilen.</span><span class="sxs-lookup"><span data-stu-id="89871-117">Contention for individual rows.</span></span> <span data-ttu-id="89871-118">Das Konfliktpotenzial steigt mit der Anzahl der Transaktionen, die versuchen, dieselbe Zeile zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="89871-118">The potential for conflicts increases as the number of transactions attempting to update the same row increases.</span></span>  
  
-   <span data-ttu-id="89871-119">Anzahl der von REPEATABLE READ-Transaktionen gelesenen Zeilen.</span><span class="sxs-lookup"><span data-stu-id="89871-119">Number of rows read by REPEATABLE READ transactions.</span></span> <span data-ttu-id="89871-120">Je mehr Zeilen gelesen werden, desto größer ist die Wahrscheinlichkeit, dass einige dieser Zeilen durch gleichzeitige Transaktionen aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="89871-120">The more rows read, the greater the chance that some of these rows are updated by concurrent transactions.</span></span> <span data-ttu-id="89871-121">Dies führt zu REPEATABLE READ-Überprüfungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="89871-121">This causes repeatable read validation failures.</span></span>  
  
-   <span data-ttu-id="89871-122">Größe der Scanbereiche, die von SERIALIZABLE-Transaktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89871-122">Size of the scan ranges used by SERIALIZABLE transactions.</span></span> <span data-ttu-id="89871-123">Je größer die Scanbereiche, je höher die Wahrscheinlichkeit, dass durch gleichzeitige Transaktionen Phantomzeilen entstehen, die SERIALIZABLE-Überprüfungsfehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="89871-123">The larger the scan ranges, the higher the chance that concurrent transactions will introduce phantom rows, causing serializable validation failures.</span></span>  
  
     <span data-ttu-id="89871-124">Es ist schwierig für eine Anwendung, diese Konflikte zu vermeiden, was Wiederholungslogik erforderlich macht.</span><span class="sxs-lookup"><span data-stu-id="89871-124">It is difficult for an application to avoid these conflicts, requiring retry logic.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="89871-125">Lese-/Schreibtransaktionen, die auf speicheroptimierte Tabellen zugreifen, erfordern Wiederholungslogik.</span><span class="sxs-lookup"><span data-stu-id="89871-125">Read-write transactions that access memory-optimized tables require retry logic.</span></span>  
  
### <a name="considerations-for-read-only-transactions-and-natively-compiled-stored-procedures"></a><span data-ttu-id="89871-126">Überlegungen zu schreibgeschützten Transaktionen und systemintern kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="89871-126">Considerations for Read-Only Transactions and Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="89871-127">Schreibgeschützte Transaktionen, die eine einzelne Ausführung einer systemintern kompilierten gespeicherten Prozedur enthalten, benötigen keine Überprüfung auf REPEATABLE READ- und SERIALIZABLE-Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="89871-127">Read-only transactions that span a single execution of a natively compiled stored procedure do not require validation for REPEATABLE READ and SERIALIZABLE transactions.</span></span> <span data-ttu-id="89871-128">Schreibkonflikte können auftreten, weil eine Transaktion schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="89871-128">Write conflicts cannot occur due to a transaction being read-only.</span></span>  
  
 <span data-ttu-id="89871-129">Abhängigkeitsfehler können jedoch weiterhin auftreten.</span><span class="sxs-lookup"><span data-stu-id="89871-129">However, dependency failures can still occur.</span></span> <span data-ttu-id="89871-130">Abhängigkeitsfehler sind seltener als Fehler, die aus Konflikten entstehen.</span><span class="sxs-lookup"><span data-stu-id="89871-130">Dependency failures are rarer than errors resulting from conflicts.</span></span> <span data-ttu-id="89871-131">Daher ist bei schreibgeschützten Transaktionen, die einzelne Ausführungen systemintern kompilierter gespeicherter Prozeduren enthalten, in vielen Fällen keine spezifische Wiederholungslogik erforderlich.</span><span class="sxs-lookup"><span data-stu-id="89871-131">Therefore, in many cases, specific retry logic is not required for read-only transactions that span single executions of natively compiled stored procedures.</span></span>  
  
### <a name="considerations-for-read-only-transactions-and-cross-container-transactions"></a><span data-ttu-id="89871-132">Überlegungen zu schreibgeschützten Transaktionen und containerübergreifenden Transaktionen</span><span class="sxs-lookup"><span data-stu-id="89871-132">Considerations for Read-Only Transactions and Cross-Container Transactions</span></span>  
 <span data-ttu-id="89871-133">Schreibgeschützte containerübergreifende Transaktionen, die Transaktionen sind, die außerhalb des Kontexts einer systemintern kompilierten gespeicherten Prozedur gestartet werden, führen keine Überprüfung aus, wenn auf alle speicheroptimierten Tabellen unter der SNAPSHOT-Isolation zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="89871-133">Read-only cross-container transactions, which are transactions that are started outside the context of a natively compiled stored procedure, do not perform validation if the memory-optimized tables are all accessed under SNAPSHOT isolation.</span></span> <span data-ttu-id="89871-134">Wenn auf speicheroptimierte Tabellen unter REPEATABLE READ- oder SERIALIZABLE-Isolation zugegriffen wird, wird allerdings zum Commitzeitpunkt eine Überprüfung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="89871-134">However, when memory-optimized tables are accessed under REPEATABLE READ or SERIALIZABLE isolation, validation is performed at commit time.</span></span> <span data-ttu-id="89871-135">In diesem Fall kann Wiederholungslogik erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="89871-135">In this case, retry logic may be required.</span></span>  
  
 <span data-ttu-id="89871-136">Weitere Informationen finden Sie im Abschnitt über Container übergreifende Transaktionen in [Transaktions Isolations Stufen](../../2014/database-engine/transaction-isolation-levels.md).</span><span class="sxs-lookup"><span data-stu-id="89871-136">For more information, see the section on Cross-Container Transactions in [Transaction Isolation Levels](../../2014/database-engine/transaction-isolation-levels.md).</span></span>  
  
## <a name="implementing-retry-logic"></a><span data-ttu-id="89871-137">Implementieren von Wiederholungslogik</span><span class="sxs-lookup"><span data-stu-id="89871-137">Implementing Retry Logic</span></span>  
 <span data-ttu-id="89871-138">Wie bei allen Transaktionen, die auf speicheroptimierte Tabellen zugreifen, müssen Sie Wiederholungslogik vorsehen, um mögliche Fehler wie Schreibkonflikte (Fehlercode 41302) oder Abhängigkeitsfehler (Fehlercode 41301) zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="89871-138">As with all transactions that access memory-optimized tables, you need to consider retry logic to handle potential failures, such as write conflicts (error code 41302) or dependency failures (error code 41301).</span></span> <span data-ttu-id="89871-139">Obwohl die Fehlerrate in den meisten Anwendungen gering ausfällt, müssen Fehler durch eine Wiederholung der Transaktion behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="89871-139">In most applications the failure rate will be low, but it is still necessary to handle failures by retrying the transaction.</span></span> <span data-ttu-id="89871-140">Es gibt zwei Möglichkeiten, Wiederholungslogik zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="89871-140">Two suggested ways of implementing retry logic are:</span></span>  
  
-   <span data-ttu-id="89871-141">Wiederholungen auf Clientseite.</span><span class="sxs-lookup"><span data-stu-id="89871-141">Client-side retries.</span></span> <span data-ttu-id="89871-142">Im Allgemeinen empfiehlt es sich, Wiederholungslogik auf Clientseite zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="89871-142">Client-side retries is the preferred way to implement retry logic in the general case.</span></span> <span data-ttu-id="89871-143">Die Clientanwendung fängt den von der Transaktion ausgelösten Fehler ab und wiederholt die Transaktion.</span><span class="sxs-lookup"><span data-stu-id="89871-143">The client application catches the error thrown by the transaction, and retries the transaction.</span></span> <span data-ttu-id="89871-144">Wenn eine vorhandene Clientanwendung über Wiederholungslogik zum Behandeln von Deadlocks verfügt, können Sie die Anwendung für die Behandlung der neuen Fehlercodes erweitern.</span><span class="sxs-lookup"><span data-stu-id="89871-144">If an existing client application has retry logic to handle deadlocks, you can extend the application to handle the new error codes.</span></span>  
  
-   <span data-ttu-id="89871-145">Verwenden einer gespeicherten Wrapperprozedur.</span><span class="sxs-lookup"><span data-stu-id="89871-145">Using a wrapper stored procedure.</span></span> <span data-ttu-id="89871-146">Der Client ruft eine gespeicherte Prozedur mit interpretiertem [!INCLUDE[tsql](../includes/tsql-md.md)] auf, die die systemintern kompilierte gespeicherte Prozedur aufruft oder die Transaktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="89871-146">The client calls an interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] stored procedure that calls the natively compiled stored procedure or executes the transaction.</span></span> <span data-ttu-id="89871-147">Die Wrapperprozedur fängt den Fehler anschließend unter Verwendung von Try/Catch-Logik ab und wiederholt den Prozeduraufruf nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="89871-147">The wrapper procedure then uses try/catch logic to catch the error and retry the procedure call if needed.</span></span> <span data-ttu-id="89871-148">Es ist möglich, dass die Ergebnisse vor dem Fehler an den Client zurückgegeben werden und der Client nicht angewiesen wird, die Ergebnisse zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="89871-148">It is possible that results are returned to the client before the failure, and the client would not know to discard them.</span></span> <span data-ttu-id="89871-149">Zur Sicherheit empfiehlt es sich, diese Methode nur mit systemintern kompilierten gespeicherten Prozeduren zu verwenden, die keine Resultsets an den Client zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="89871-149">Therefore, to be safe, it is best to use this method only with natively compiled stored procedures that do not return any result sets to the client.</span></span>  
  
 <span data-ttu-id="89871-150">Die Wiederholungslogik kann entweder in [!INCLUDE[tsql](../includes/tsql-md.md)] oder im Anwendungscode auf der mittleren Ebene implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="89871-150">The retry logic can be implemented either in [!INCLUDE[tsql](../includes/tsql-md.md)] or in the application code in the mid-tier.</span></span>  
  
 <span data-ttu-id="89871-151">Zwei mögliche Gründe, Wiederholungslogik in Erwägung zu ziehen:</span><span class="sxs-lookup"><span data-stu-id="89871-151">Two possible reasons to consider the retry logic are:</span></span>  
  
-   <span data-ttu-id="89871-152">Die Clientanwendung verfügt über Wiederholungslogik für andere Fehlercodes, wie 1205, die Sie erweitern können.</span><span class="sxs-lookup"><span data-stu-id="89871-152">The client application has retry logic for other error codes, such as 1205, which you can extend.</span></span>  
  
-   <span data-ttu-id="89871-153">Konflikte sind selten, und ist es wichtig, die End-to-End-Latenzzeit mithilfe einer vorbereiteten Ausführung zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="89871-153">Conflicts are rare, and it is important to reduce end-to-end latency by using prepared execution.</span></span> <span data-ttu-id="89871-154">Weitere Informationen zum direkten Ausführen von System intern kompilierten gespeicherten Prozeduren finden Sie unter [nativ kompilierte gespeicherte Prozeduren](../relational-databases/in-memory-oltp/natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="89871-154">For more information about executing natively compiled stored procedures directly, see [Natively Compiled Stored Procedures](../relational-databases/in-memory-oltp/natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="89871-155">Das folgende Beispiel zeigt Wiederholungslogik in einer interpretierten gespeicherten [!INCLUDE[tsql](../includes/tsql-md.md)]-Prozedur, die einen Aufruf einer systemintern kompilierten gespeicherten Prozedur oder einer containerübergreifenden Transaktion enthält.</span><span class="sxs-lookup"><span data-stu-id="89871-155">The following sample shows retry logic in an interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] stored procedure that contains a call either to a natively compiled stored procedure or to a cross-container transaction.</span></span>  
  
```sql  
CREATE PROCEDURE usp_my_procedure @param1 type1, @param2 type2, ...  
AS  
BEGIN  
  -- number of retries - tune based on the workload  
  DECLARE @retry INT = 10  
  
  WHILE (@retry > 0)  
  BEGIN  
    BEGIN TRY  
  
      -- exec usp_my_native_proc @param1, @param2, ...  
  
      --       or  
  
      -- BEGIN TRANSACTION  
      --   ...  
      -- COMMIT TRANSACTION  
  
      SET @retry = 0  
    END TRY  
    BEGIN CATCH  
      SET @retry -= 1  
  
      -- the error number for deadlocks (1205) does not need to be included for   
      -- transactions that do not access disk-based tables  
      IF (@retry > 0 AND error_number() in (41302, 41305, 41325, 41301, 1205))  
      BEGIN  
        -- these error conditions are transaction dooming - rollback the transaction  
        -- this is not needed if the transaction spans a single native proc execution  
        --   as the native proc will simply rollback when an error is thrown   
        IF XACT_STATE() = -1  
          ROLLBACK TRANSACTION  
  
        -- use a delay if there is a high rate of write conflicts (41302)  
        --   length of delay should depend on the typical duration of conflicting transactions  
        -- WAITFOR DELAY '00:00:00.001'  
      END  
      ELSE  
      BEGIN  
        -- insert custom error handling for other error conditions here  
  
        -- throw if this is not a qualifying error condition  
        ;THROW  
      END  
    END CATCH  
  END  
END  
```  
  
## <a name="see-also"></a><span data-ttu-id="89871-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89871-156">See Also</span></span>  
 <span data-ttu-id="89871-157">[Grundlegendes zu Transaktionen in Speicher optimierten Tabellen](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="89871-157">[Understanding Transactions on Memory-Optimized Tables](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="89871-158">[Transaktionen in Speicher optimierten Tabellen](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="89871-158">[Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="89871-159">Richtlinien für Transaktionsisolationsstufen mit speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="89871-159">Guidelines for Transaction Isolation Levels with Memory-Optimized Tables</span></span>](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md)  
  
  
