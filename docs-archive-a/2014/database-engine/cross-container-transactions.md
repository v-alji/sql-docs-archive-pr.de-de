---
title: Container übergreifende Transaktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5d84b51a-ec17-4c5c-b80e-9e994fc8ae80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28437f0903459616a574e713c0f138e8bb459870
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618250"
---
# <a name="cross-container-transactions"></a><span data-ttu-id="432ac-102">Containerübergreifende Transaktionen</span><span class="sxs-lookup"><span data-stu-id="432ac-102">Cross-Container Transactions</span></span>
  <span data-ttu-id="432ac-103">Containerübergreifende Transaktionen sind entweder implizite oder explizite Benutzertransaktionen, die Aufrufe von systemintern kompilierten gespeicherten Prozeduren oder Vorgängen für speicheroptimierte Tabellen enthalten.</span><span class="sxs-lookup"><span data-stu-id="432ac-103">Cross-container transactions are either implicit or explicit user transactions that include calls to natively-compiled stored procedures or operations on memory-optimized tables.</span></span>  
  
 <span data-ttu-id="432ac-104">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] lösen Aufrufe von gespeicherten Prozeduren keine Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="432ac-104">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], calls to stored procedures do not initiate a transaction.</span></span> <span data-ttu-id="432ac-105">Ausführungen von systemintern kompilierten Prozeduren im Autocommitmodus (nicht im Kontext einer Benutzertransaktion) werden nicht als containerübergreifende Transaktionen angesehen.</span><span class="sxs-lookup"><span data-stu-id="432ac-105">Executions of natively compiled procedures in autocommit mode (not in the context of a user transaction) are not considered cross-container transactions.</span></span>  
  
 <span data-ttu-id="432ac-106">Jede interpretierte Abfrage, die auf speicheroptimierte Tabellen verweist, wird als Teil einer containerübergreifenden Transaktion angesehen. Dies gilt unabhängig davon, ob die Abfrage über eine explizite oder implizite Transaktion oder im Autocommitmodus ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="432ac-106">Any interpreted query that references memory-optimized tables is considered a part of a cross-container transaction, whether executed from an explicit or implicit transaction or in auto-commit mode.</span></span>  
  
##  <a name="isolation-of-individual-operations"></a><a name="isolation"></a><span data-ttu-id="432ac-107">Isolierung einzelner Vorgänge</span><span class="sxs-lookup"><span data-stu-id="432ac-107">Isolation of Individual Operations</span></span>  
 <span data-ttu-id="432ac-108">Jede [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Transaktion hat eine Isolationsstufe.</span><span class="sxs-lookup"><span data-stu-id="432ac-108">Each [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] transaction has an isolation level.</span></span> <span data-ttu-id="432ac-109">Die Standardisolationsstufe ist Read Committed.</span><span class="sxs-lookup"><span data-stu-id="432ac-109">The default isolation level is Read Committed.</span></span> <span data-ttu-id="432ac-110">Wenn Sie eine andere Isolationsstufe verwenden möchten, können Sie die Isolationsstufe mithilfe von [Set Transaction Isolation Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql)festlegen.</span><span class="sxs-lookup"><span data-stu-id="432ac-110">To use a different isolation level, you can set the isolation level using [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
 <span data-ttu-id="432ac-111">Häufig ist es notwendig, Vorgänge in speicheroptimierten Tabellen auf einer anderen Isolationsstufe als Vorgänge in datenträgerbasierten Tabellen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="432ac-111">It is often necessary to perform operations on memory-optimized tables at a different isolation level than operations on disk-based tables.</span></span> <span data-ttu-id="432ac-112">In einer Transaktion ist es möglich, eine andere Isolationsstufe für eine Auflistung von Anweisungen oder für einen einzelnen Lesevorgang festzulegen.</span><span class="sxs-lookup"><span data-stu-id="432ac-112">In a transaction, it is possible to set a different isolation level for a collection of statements or for an individual read operation.</span></span>  
  
### <a name="specifying-the-isolation-level-of-individual-operations"></a><span data-ttu-id="432ac-113">Angeben der Isolationsstufe bei einzelnen Vorgängen</span><span class="sxs-lookup"><span data-stu-id="432ac-113">Specifying the Isolation Level of Individual Operations</span></span>  
 <span data-ttu-id="432ac-114">Um eine andere Isolationsstufe für eine Gruppe von Anweisungen in einer Transaktion festzulegen, können Sie `SET TRANSACTION ISOLATION LEVEL` verwenden.</span><span class="sxs-lookup"><span data-stu-id="432ac-114">To set a different isolation level for a set of statements in a transaction, you can use `SET TRANSACTION ISOLATION LEVEL`.</span></span> <span data-ttu-id="432ac-115">Im folgenden Beispiel einer Transaktion wird die Serializable-Isolationsstufe als Standard verwendet.</span><span class="sxs-lookup"><span data-stu-id="432ac-115">The following example of a transaction uses the serializable isolation level as default.</span></span> <span data-ttu-id="432ac-116">Die Einfüge- und Auswahlvorgänge in t3, t2 und t1 werden in Repeatable Read-Isolation ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="432ac-116">The insert and select operations on t3, t2, and t1 are executed under repeatable read isolation.</span></span>  
  
```sql  
set transaction isolation level serializable  
go  
  
begin transaction  
 ......  
  set transaction isolation level repeatable read  
  
  insert t3 select * from t1 join t2 on t1.id=t2.id  
  
  set transaction isolation level serializable  
 ......  
commit  
```  
  
 <span data-ttu-id="432ac-117">Um eine Isolationsstufe für einzelne Lesevorgänge festzulegen, die vom Transaktionsstandard abweicht, können Sie einen Tabellenhinweis verwenden (z. B. Serializable).</span><span class="sxs-lookup"><span data-stu-id="432ac-117">To set an isolation level for individual read operations that is different from the transaction default, you can use a table hint (for example, serializable).</span></span> <span data-ttu-id="432ac-118">Jede Auswahl entspricht einem Lesevorgang, und jedes Update und jede Löschung entsprechen einem Lesevorgang, da die Zeile immer gelesen werden muss, bevor sie aktualisiert oder gelöscht werden kann.</span><span class="sxs-lookup"><span data-stu-id="432ac-118">Every select corresponds to a read operation and every update and every delete corresponds to a read, because the row always needs to be read before it can be updated or deleted.</span></span> <span data-ttu-id="432ac-119">Einfügevorgänge haben keine Isolationsstufe, da Schreibvorgänge in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] immer isoliert ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="432ac-119">Insert operations do not have an isolation level, because writes are always isolated in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="432ac-120">Im folgenden Beispiel wird die Standardisolationsstufe Read Committed verwendet. Auf Tabelle t1 wird jedoch mit Serializable-Isolation und auf t2 mit Snapshot-Isolation zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="432ac-120">In the following example, the default isolation level for the transaction is read committed, but table t1 is accessed under serializable and t2 under snapshot isolation.</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
 ......  
  
  insert t3 select * from t1 (serializable) join t2 (snapshot) on t1.id=t2.id  
  
  ......  
commit  
```  
  
### <a name="isolation-semantics-for-individual-operations"></a><span data-ttu-id="432ac-121">Isolationssemantik für einzelne Vorgänge</span><span class="sxs-lookup"><span data-stu-id="432ac-121">Isolation Semantics for Individual Operations</span></span>  
 <span data-ttu-id="432ac-122">Eine serialisierbare Transaktion T wird in vollständiger Isolation ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="432ac-122">A serializable transaction T is executed in complete isolation.</span></span> <span data-ttu-id="432ac-123">Dabei wird angenommen, dass für alle anderen Transaktionen vor dem Start von T ein Commit ausgeführt wurde oder dass alle anderen Transaktionen erst gestartet werden, nachdem für T ein Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="432ac-123">It is as if every other transaction has either committed before T started, or is started after T committed.</span></span> <span data-ttu-id="432ac-124">Noch komplexer wird es, wenn verschiedene Vorgänge in einer Transaktion über unterschiedliche Isolationsstufen verfügen.</span><span class="sxs-lookup"><span data-stu-id="432ac-124">It becomes more complex when different operations in a transaction have different isolation levels.</span></span>  
  
 <span data-ttu-id="432ac-125">Die allgemeine Semantik der Transaktions Isolations Stufen in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sowie die Auswirkungen auf das Sperren wird unter [Set Transaction Isolation Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql)erläutert.</span><span class="sxs-lookup"><span data-stu-id="432ac-125">The general semantics of the transaction isolation levels in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], along with the implications on locking, is explained in [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
 <span data-ttu-id="432ac-126">Bei containerübergreifenden Transaktionen, in denen verschiedene Vorgänge über unterschiedliche Isolationsstufen verfügen können, sollten Sie sich die Semantik für die Isolation einzelner Lesevorgänge verdeutlichen.</span><span class="sxs-lookup"><span data-stu-id="432ac-126">For cross-container transactions where different operations may have different isolation levels, you need to understand the semantics of isolation of individual read operations.</span></span> <span data-ttu-id="432ac-127">Schreibvorgänge sind immer isoliert.</span><span class="sxs-lookup"><span data-stu-id="432ac-127">Write operations are always isolated.</span></span> <span data-ttu-id="432ac-128">Schreibvorgänge in verschiedenen Transaktionen haben keine Auswirkungen aufeinander.</span><span class="sxs-lookup"><span data-stu-id="432ac-128">Writes in different transactions cannot impact each other.</span></span>  
  
 <span data-ttu-id="432ac-129">Ein Datenlesevorgang gibt mehrere Zeilen zurück, die eine Filterbedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="432ac-129">A data read operation returns a number of rows that satisfy a filter condition.</span></span>  
  
 <span data-ttu-id="432ac-130">Lesevorgänge werden als Teil einer Transaktion T ausgeführt. die Isolations Stufen für Lesevorgänge können im Hinblick auf</span><span class="sxs-lookup"><span data-stu-id="432ac-130">Reads are performed as part of a transaction T. Isolation levels for read operations can be understood in terms of,</span></span>  
  
 <span data-ttu-id="432ac-131">Commitstatus</span><span class="sxs-lookup"><span data-stu-id="432ac-131">Commit Status</span></span>  
 <span data-ttu-id="432ac-132">Der Commitstatus bezieht sich darauf, ob für den Datenlesevorgang garantiert ein Commit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="432ac-132">Commit status refers to whether the data read is guaranteed to be committed.</span></span>  
  
 <span data-ttu-id="432ac-133">(Transaktionale) Konsistenz</span><span class="sxs-lookup"><span data-stu-id="432ac-133">(Transactional) Consistency</span></span>  
 <span data-ttu-id="432ac-134">Transaktionskonsistenz für einen Satz von Lesevorgängen bezieht sich auf die Frage, ob alle gelesenen Zeilenversionen garantiert Updates aus exakt demselben Transaktionssatz enthalten.</span><span class="sxs-lookup"><span data-stu-id="432ac-134">Transactional consistency for a set of reads refers to whether the row versions read are all guaranteed to include updates from precisely the same set of transactions.</span></span>  
  
 <span data-ttu-id="432ac-135">Stabilitätsgarantien, die das System der Transaktion T im Hinblick auf den Lesevorgang gewährt.</span><span class="sxs-lookup"><span data-stu-id="432ac-135">Stability guarantees the system gives to transaction T about the data read.</span></span>  
 <span data-ttu-id="432ac-136">Stabilität bezieht sich darauf, ob die Lesevorgänge der Transaktion wiederholbar sind.</span><span class="sxs-lookup"><span data-stu-id="432ac-136">Stability refers to whether the transaction's reads are repeatable.</span></span> <span data-ttu-id="432ac-137">Würden die Lesevorgänge bei einer Wiederholung dieselben Zeilen und Zeilenversionen zurückgeben?</span><span class="sxs-lookup"><span data-stu-id="432ac-137">That is, if the reads were repeated would they return the same rows and row versions?</span></span>  
  
 <span data-ttu-id="432ac-138">Bestimmte Garantien beziehen sich auf die logische Beendigungszeit der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="432ac-138">Certain guarantees refer to the logical end time of the transaction.</span></span> <span data-ttu-id="432ac-139">In der Regel ist die logische Beendigungszeit der Zeitpunkt, zu dem für die Transaktion ein Commit in der Datenbank ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="432ac-139">In general, the logical end time is the time the transaction is committed to the database.</span></span> <span data-ttu-id="432ac-140">Wenn die Transaktion auf speicheroptimierte Tabellen zugreift, ist die logische Beendigungszeit technisch gesehen der Anfang der Überprüfungsphase.</span><span class="sxs-lookup"><span data-stu-id="432ac-140">If memory-optimized tables are accessed by the transaction, the logical end time is technically the beginning of the validation phase.</span></span> <span data-ttu-id="432ac-141">(Weitere Informationen finden Sie in der Erörterung der Transaktions Lebensdauer unter [Transaktionen in Speicher optimierten Tabellen](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="432ac-141">(For more information, see the transaction lifetime discussion in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="432ac-142">Für eine Transaktion (t) sind eigene Updates unabhängig von der Isolationsstufe immer sichtbar:</span><span class="sxs-lookup"><span data-stu-id="432ac-142">Regardless of isolation level, a transaction (T) always sees its own updates:</span></span>  
  
 <span data-ttu-id="432ac-143">READ UNCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="432ac-143">READ UNCOMMITTED</span></span>  
 <span data-ttu-id="432ac-144">Für die gelesenen Daten, die unter Umständen weder konsistent noch stabil sind, wird möglicherweise kein Commit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="432ac-144">The data read may neither be committed, consistent, or stable.</span></span> <span data-ttu-id="432ac-145">Sie enthalten jedoch frühere Schreibvorgänge, die von T vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="432ac-145">However, it will include earlier write operations done by T.</span></span>  
  
 <span data-ttu-id="432ac-146">READ COMMITTED</span><span class="sxs-lookup"><span data-stu-id="432ac-146">READ COMMITTED</span></span>  
 <span data-ttu-id="432ac-147">Für die gelesenen Daten wird ein Commit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="432ac-147">The data read will be committed.</span></span>  
  
 <span data-ttu-id="432ac-148">SNAPSHOT</span><span class="sxs-lookup"><span data-stu-id="432ac-148">SNAPSHOT</span></span>  
 <span data-ttu-id="432ac-149">Alle Lesevorgänge, die von T per Snapshot-Isolation ausgeführt wurden, haben die gleiche logische Lesezeit, nämlich den Beginn der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="432ac-149">All read operations performed by T under snapshot isolation have the same logical read time, which is the beginning of the transaction.</span></span> <span data-ttu-id="432ac-150">Für die gelesenen Daten wird garantiert ein Commit ausgeführt, und sie sind ab der logischen Lesezeit konsistent.</span><span class="sxs-lookup"><span data-stu-id="432ac-150">The data read is guaranteed to be committed and consistent as of the logical read time.</span></span> <span data-ttu-id="432ac-151">Wenn ein Lesevorgang ab der ursprünglichen Lesezeit wiederholt wird, wird garantiert das gleiche Ergebnis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="432ac-151">Repeating a read as of the original read time is guaranteed to return the same result.</span></span>  
  
 <span data-ttu-id="432ac-152">REPEATABLE READ</span><span class="sxs-lookup"><span data-stu-id="432ac-152">REPEATABLE READ</span></span>  
 <span data-ttu-id="432ac-153">Für die gelesenen Daten wird garantiert ein Commit ausgeführt, und die Stabilität wird zur logischen Beendigungszeit der Transaktion erhöht.</span><span class="sxs-lookup"><span data-stu-id="432ac-153">The data read is guaranteed to be committed and stable up to the logical end time of the transaction.</span></span>  
  
 <span data-ttu-id="432ac-154">SERIALIZABLE</span><span class="sxs-lookup"><span data-stu-id="432ac-154">SERIALIZABLE</span></span>  
 <span data-ttu-id="432ac-155">Alle Garantien von Repeatable Read zuzüglich Phantom Vermeidung und Transaktions Konsistenz in Bezug auf alle serialisierbaren Lesevorgänge, die von t. Phantom Vermeidung durchgeführt werden, bedeutet, dass der Scanvorgang nur zusätzliche Zeilen zurückgeben kann, die von t geschrieben wurden, aber keine Zeilen, die von anderen Transaktionen geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="432ac-155">All guarantees of REPEATABLE READ plus phantom avoidance and transactional consistency with respect to all serializable read operations performed by T. Phantom avoidance means that the scan operation can only return additional rows that were written by T, but no rows that were written by other transactions.</span></span>  
  
 <span data-ttu-id="432ac-156">Beachten Sie die folgende Transaktion:</span><span class="sxs-lookup"><span data-stu-id="432ac-156">Consider the following transaction,</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
  -- remove all rows from t3; the related read operation is performed under read committed   
  -- isolation, as this is the default for the transaction  
  delete from t3  
  
  -- copy the contents from t1 to t3; the read on t1 is performed under the serializable   
  -- isolation level  
  insert t3 select * from t1 (serializable)  
  
  -- compare t3 and t1; note: the result set may not be empty, as rows may have been added   
  -- by other transaction before this select, due to the read committed isolation level  
  select * from t3 except t1  
  
  -- compare t1 and t3; note: the result set is empty, as no rows have been added to t1   
  -- since its contents were copied to t1, due to the serializable isolation level  
  select * from t1 except t3  
commit  
```  
  
 <span data-ttu-id="432ac-157">Diese Transaktion löscht alle Zeilen aus t3 mit Read Committed-Isolation, kopiert alle Zeilen mit Serializable-Isolation von t1 nach t3 und vergleicht dann t1 und t3.</span><span class="sxs-lookup"><span data-stu-id="432ac-157">This transaction deletes all rows from t3 under read committed isolation, copies all rows from t1 to t3 under serializable isolation, and then compares t1 and t3.</span></span> <span data-ttu-id="432ac-158">Einige Zeilen [nicht in t1] wurden möglicherweise seit der Leerung der Tabelle t3 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="432ac-158">Some rows [not in t1] may have been added to t3 since the table was emptied.</span></span> <span data-ttu-id="432ac-159">t1 wurden keine Zeilen hinzugefügt, da die Kopie serialisierbar war.</span><span class="sxs-lookup"><span data-stu-id="432ac-159">No rows were added to t1 as the copy was serializable.</span></span>  
  
 <span data-ttu-id="432ac-160">Obwohl der Lesevorgang von t1 am Ende der Transaktion syntaktisch gesehen "Read Committed" entspricht, ist er eigentlich "Serializable", da derselbe Lesevorgang schon zu einem früheren Zeitpunkt in der Transaktion mit Serializable-Isolation ausgeführt wurde: Serialisierbarkeit garantiert, dass dieselben Zeilen zurückgegeben werden, wenn der Lesevorgang zu einem späteren Zeitpunkt in der Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="432ac-160">Although the read from t1 at the end of the transaction is syntactically read committed, it is effectively serializable, because the same read was performed earlier in the transaction under serializable isolation: serializability guarantees that if the read is performed at any later point in the transaction, the same rows are returned.</span></span>  
  
## <a name="cross-container-transactions-and-isolation-levels"></a><span data-ttu-id="432ac-161">Containerübergreifende Transaktionen und Isolationsstufen</span><span class="sxs-lookup"><span data-stu-id="432ac-161">Cross-Container Transactions and Isolation Levels</span></span>  
 <span data-ttu-id="432ac-162">Eine Container übergreifende Transaktion kann als zwei Seiten betrachtet werden: eine Datenträger basierte Seite (für Vorgänge in Datenträger basierten Tabellen) und eine Speicher optimierte Seite (für Vorgänge in Speicher optimierten Tabellen).</span><span class="sxs-lookup"><span data-stu-id="432ac-162">A cross-container transaction can be seen as having two sides: a disk-based side (for operations on disk-based tables) and a memory-optimized side (for operations on memory-optimized tables).</span></span> <span data-ttu-id="432ac-163">Diese beiden Seiten können unterschiedliche Isolationsstufen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="432ac-163">These two sides may have different isolation levels.</span></span> <span data-ttu-id="432ac-164">Tatsächlich können einzelne Lesevorgänge auf jeder Seite unterschiedliche Isolationsstufen haben.</span><span class="sxs-lookup"><span data-stu-id="432ac-164">In fact, individual read operations on each side may have different isolation levels.</span></span>  
  
 <span data-ttu-id="432ac-165">Die datenträgerbasierte Seite einer gegebenen Transaktion T erreicht eine bestimmte Isolationsstufe X, wenn eine der folgenden Bedingungen erfüllt wird:</span><span class="sxs-lookup"><span data-stu-id="432ac-165">The disk-based side of a given transaction T reaches a certain isolation level X if one of the following conditions is met:</span></span>  
  
-   <span data-ttu-id="432ac-166">Sie beginnt in X. Das heißt, der Standard der Sitzung war X, weil Sie entweder ausgeführt `SET TRANSACTION ISOLATION LEVEL` haben oder der Standardwert ist [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="432ac-166">It starts in X. That is, the session default was X, either because you executed `SET TRANSACTION ISOLATION LEVEL`, or it is the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] default.</span></span>  
  
-   <span data-ttu-id="432ac-167">Während der Transaktion wird die Standardisolationsstufe mit `SET TRANSACTION ISOLATION LEVEL` in X geändert.</span><span class="sxs-lookup"><span data-stu-id="432ac-167">During the transaction, the default isolation level is changed to X using `SET TRANSACTION ISOLATION LEVEL`.</span></span>  
  
-   <span data-ttu-id="432ac-168">Ein Lesevorgang in einer datenträgerbasierten Tabelle wird mit der Isolationsstufe X und der Syntax `WITH (X)` ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="432ac-168">A read operation on a disk-based table is executed under isolation level X, using the syntax `WITH (X)`.</span></span>  
  
 <span data-ttu-id="432ac-169">Die speicheroptimierte Seite von T erreicht eine Isolationsstufe Y, wenn während der Ausführung von T ein Lesevorgang in einer speicheroptimierten Tabelle oder eine systemintern kompilierte gespeicherte Prozedur mit der Isolationsstufe Y ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="432ac-169">The memory-optimized side of T reaches an isolation level Y if during execution of T, any read operation on a memory-optimized table or any natively compiled stored procedure is executed under isolation level Y.</span></span>  
  
 <span data-ttu-id="432ac-170">Betrachten Sie die folgende Transaktion als Beispiel.</span><span class="sxs-lookup"><span data-stu-id="432ac-170">Consider the following transaction as an example.</span></span> <span data-ttu-id="432ac-171">Hier sind t1 und t2 datenträgerbasierte Tabellen und t3 und t4 speicheroptimierte Tabellen.</span><span class="sxs-lookup"><span data-stu-id="432ac-171">Here, t1 and t2 are disk-based tables and t3 and t4 are memory-optimized tables.</span></span>  
  
 <span data-ttu-id="432ac-172">Die datenträgerbasierte Seite der Transaktion erreicht die Isolationsstufe "Read Committed", da sie auf dieser Ebene beginnt.</span><span class="sxs-lookup"><span data-stu-id="432ac-172">The disk-based side of the transaction reaches the isolation level read committed, because it starts in that level.</span></span> <span data-ttu-id="432ac-173">Die datenträgerbasierte Seite erreicht auch "Repeatable Read", da der erste Lesevorgang mit dieser Isolationsstufe ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="432ac-173">The disk-based side also reaches repeatable read, because the first read operation is executed under that isolation level.</span></span> <span data-ttu-id="432ac-174">Der Löschvorgang am Ende der Transaktion wird mit der Read Committed-Isolationsstufe ausgeführt und führt daher keine neue Isolationsstufe ein.</span><span class="sxs-lookup"><span data-stu-id="432ac-174">The delete at the end of the transaction is executed under read committed isolation level, and so does not introduce a new isolation level.</span></span>  
  
 <span data-ttu-id="432ac-175">Die speicheroptimierte Seite der Transaktion kann eine von zwei Stufen erreichen: Wenn condition1 wahr ist, wird "Serializable" erreicht, und wenn sie falsch ist, erreicht die speicheroptimierte Seite lediglich die Snapshot-Isolation.</span><span class="sxs-lookup"><span data-stu-id="432ac-175">The memory-optimized side of the transaction can reach one of two levels: if condition1 is true, it reaches serializable, while if it is false, the memory-optimized side reaches only snapshot isolation.</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
  select * from t1 (repeatableread)  
  
  if condition1 begin  
    insert t3 select * from t4 (serializable)  
  end  
  else begin  
    insert t3 select * from t4 (snapshot)  
  end  
  
  delete from t1  
commit  
```  
  
### <a name="supported-isolation-levels-for-cross-container-transactions"></a><span data-ttu-id="432ac-176">Unterstützte Isolationsstufen für containerübergreifende Transaktionen</span><span class="sxs-lookup"><span data-stu-id="432ac-176">Supported Isolation Levels for Cross-Container Transactions</span></span>  
 <span data-ttu-id="432ac-177">Es gibt Einschränkungen hinsichtlich der Isolationsstufen, die bei Vorgängen in speicheroptimierten Tabellen in containerübergreifenden Transaktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="432ac-177">There are limitations on the isolation levels used with operations on memory-optimized tables in cross-container transactions.</span></span>  
  
 <span data-ttu-id="432ac-178">Speicheroptimierte Tabellen unterstützen die Isolationsstufen SNAPSHOT, REPEATABLE READ und SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="432ac-178">Memory-optimized tables support the isolation levels SNAPSHOT, REPEATABLE READ, and SERIALIZABLE.</span></span> <span data-ttu-id="432ac-179">Bei Autocommittransaktionen unterstützen speicheroptimierte Tabellen die Isolationsstufe READ COMMITTED.</span><span class="sxs-lookup"><span data-stu-id="432ac-179">For autocommit transactions, memory-optimized tables support the isolation level READ COMMITTED.</span></span>  
  
 <span data-ttu-id="432ac-180">Die folgenden Szenarien werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="432ac-180">The following scenarios are supported:</span></span>  
  
-   <span data-ttu-id="432ac-181">Containerübergreifende READ UNCOMMITTED-, READ COMMITTED- und READ_COMMITTED_SNAPSHOT-Transaktionen können mit SNAPSHOT-, REPEATABLE READ- und SERIALIZABLE-Isolation auf speicheroptimierte Tabellen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="432ac-181">READ UNCOMMITTED, READ COMMITTED, and READ_COMMITTED_SNAPSHOT cross-container transactions can access memory-optimized tables under SNAPSHOT, REPEATABLE READ, and SERIALIZABLE isolation.</span></span> <span data-ttu-id="432ac-182">Die READ COMMITTED-Garantie bedeutet für die Transaktion, dass für alle Zeilen, die von der Transaktion gelesen wurden, ein Commit in der Datenbank ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="432ac-182">The READ COMMITTED guarantee holds for the transaction; all rows read by the transaction have been committed to the database.</span></span>  
  
-   <span data-ttu-id="432ac-183">REPEATABLE READ- und SERIALIZABLE-Transaktionen können mit der SNAPSHOT-Isolation auf speicheroptimierte Tabellen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="432ac-183">REPEATABLE READ and SERIALIZABLE transactions can access memory-optimized tables under SNAPSHOT isolation.</span></span>  
  
## <a name="read-only-cross-container-transactions"></a><span data-ttu-id="432ac-184">Schreibgeschützte containerübergreifende Transaktionen</span><span class="sxs-lookup"><span data-stu-id="432ac-184">Read-only Cross-Container Transactions</span></span>  
 <span data-ttu-id="432ac-185">Für die meisten schreibgeschützten Transaktionen in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] wird zur Commitzeit ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="432ac-185">Most read-only transactions in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] are rolled back at commit time.</span></span> <span data-ttu-id="432ac-186">Da es keine Änderungen gibt, für die ein Commit in der Datenbank ausgeführt wird, gibt das System einfach die Ressourcen frei, die von der Transaktion verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="432ac-186">Because there are no changes to commit to the database, the system simply frees the resources used by the transaction.</span></span> <span data-ttu-id="432ac-187">Für schreibgeschützte datenträgerbasierte Transaktionen werden alle von der Transaktion vorgenommenen Sperren zu diesem Zeitpunkt aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="432ac-187">For read-only disk-based transactions, all locks taken by the transaction are released at this time.</span></span> <span data-ttu-id="432ac-188">Für schreibgeschützte speicheroptimierte Transaktionen, die die Ausführung einer einzelnen systemintern kompilierten Prozedur umfassen, wird keine Überprüfung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="432ac-188">For read-only memory-optimized transactions that span a single natively compiled procedure execution, no validation is performed.</span></span>  
  
 <span data-ttu-id="432ac-189">Für containerübergreifende schreibgeschützte Transaktionen im Autocommitmodus wird einfach am Ende der Transaktion ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="432ac-189">Cross-container, read-only transactions in autocommit mode are simply rolled back at the end of the transaction.</span></span> <span data-ttu-id="432ac-190">Es wird keine Überprüfung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="432ac-190">No validation is performed.</span></span>  
  
 <span data-ttu-id="432ac-191">Explizite oder implizite containerübergreifende schreibgeschützte Transaktionen führen die Überprüfung zur Commitzeit aus, wenn die Transaktion mit REPEATABLE READ- oder SERIALIZABLE-Isolation auf speicheroptimierte Tabellen zugreift.</span><span class="sxs-lookup"><span data-stu-id="432ac-191">Explicit or implicit cross-container, read-only transactions perform validation at commit time if the transaction accesses memory-optimized tables under REPEATABLE READ or SERIALIZABLE isolation.</span></span> <span data-ttu-id="432ac-192">Ausführliche Informationen zur Validierung finden Sie im Abschnitt zu Konflikterkennung, Validierung und Commit-Abhängigkeits Prüfungen in [Transaktionen in Speicher optimierten Tabellen](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="432ac-192">For details about validation see the section on Conflict Detection, Validation, and Commit Dependency Checks in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="432ac-193">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="432ac-193">See Also</span></span>  
 <span data-ttu-id="432ac-194">[Grundlegendes zu Transaktionen in Speicher optimierten Tabellen](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="432ac-194">[Understanding Transactions on Memory-Optimized Tables](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="432ac-195">[Richtlinien für Transaktions Isolations Stufen mit Speicher optimierten Tabellen](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="432ac-195">[Guidelines for Transaction Isolation Levels with Memory-Optimized Tables](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="432ac-196">Richtlinien zur Wiederholungslogik für Transaktionen auf speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="432ac-196">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>](../../2014/database-engine/guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)  
  
  
