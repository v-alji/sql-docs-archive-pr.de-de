---
title: Atomic-Blöcke | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 40e0e749-260c-4cfc-a848-444d30c09d85
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ca8f5b4d767ef0fe836cd260f8d12dd5b40c75d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609207"
---
# <a name="atomic-blocks"></a><span data-ttu-id="887d8-102">ATOMIC-Blöcke</span><span class="sxs-lookup"><span data-stu-id="887d8-102">Atomic Blocks</span></span>
  <span data-ttu-id="887d8-103">`BEGIN ATOMIC` ist Teil des ANSI SQL-Standards.</span><span class="sxs-lookup"><span data-stu-id="887d8-103">`BEGIN ATOMIC` is part of the ANSI SQL standard.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="887d8-104">unterstützt ATOMIC-Blöcke nur auf der obersten Ebene systemintern kompilierter gespeicherter Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="887d8-104">supports atomic blocks only at the top-level of natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="887d8-105">Jede systemintern kompilierte gespeicherte Prozedur enthält genau einen Block mit [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="887d8-105">Every natively compiled stored procedure contains exactly one block of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="887d8-106">Dies ist ein ATOMIC-Block.</span><span class="sxs-lookup"><span data-stu-id="887d8-106">This is an ATOMIC block.</span></span>  
  
-   <span data-ttu-id="887d8-107">Nicht systemeigene interpretierte gespeicherte [!INCLUDE[tsql](../../includes/tsql-md.md)] -Prozeduren und Ad-hoc-Batches unterstützen keine ATOMIC-Blöcke.</span><span class="sxs-lookup"><span data-stu-id="887d8-107">Non-native, interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and ad hoc batches do not support atomic blocks.</span></span>  
  
 <span data-ttu-id="887d8-108">ATOMIC-Blöcke werden (unteilbar) innerhalb der Transaktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="887d8-108">Atomic blocks are executed (atomically) within the transaction.</span></span> <span data-ttu-id="887d8-109">Entweder werden alle Anweisungen im Block erfolgreich ausgeführt, oder für den gesamten Block wird ein Rollback zu dem Sicherungspunkt ausgeführt, der beim Starten des Blocks erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="887d8-109">Either all statements in the block succeed or the entire block will be rolled back to the savepoint that was created at the start of the block.</span></span> <span data-ttu-id="887d8-110">Darüber hinaus sind die Sitzungseinstellungen für den ATOMIC-Block fest definiert.</span><span class="sxs-lookup"><span data-stu-id="887d8-110">In addition, the session settings are fixed for the atomic block.</span></span> <span data-ttu-id="887d8-111">Wird derselbe ATOMIC-Block in Sitzungen mit unterschiedlichen Einstellungen ausgeführt, ergibt sich unabhängig von den Einstellungen der aktuellen Sitzung dasselbe Verhalten.</span><span class="sxs-lookup"><span data-stu-id="887d8-111">Executing the same atomic block in sessions with different settings will result in the same behavior, independent of the settings of the current session.</span></span>  
  
## <a name="transactions-and-error-handling"></a><span data-ttu-id="887d8-112">Transaktionen und Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="887d8-112">Transactions and Error Handling</span></span>  
 <span data-ttu-id="887d8-113">Wenn in einer Sitzung bereits eine Transaktion vorhanden ist (da von einem Batch eine `BEGIN TRANSACTION`-Anweisung ausgeführt wurde und die Transaktion aktiv bleibt), wird durch das Starten eines ATOMIC-Blocks in der Transaktion ein Sicherungspunkt erstellt.</span><span class="sxs-lookup"><span data-stu-id="887d8-113">If a transaction already exists on a session (because a batch executed a `BEGIN TRANSACTION` statement and the transaction remains active), then starting an atomic block will create a savepoint in the transaction.</span></span> <span data-ttu-id="887d8-114">Wenn der Block ohne Ausnahme beendet wird, wird der erstellte Sicherungspunkt für den Block festgeschrieben. Für die Transaktion wird jedoch erst ein Commit ausgeführt, wenn für die Transaktion auf Sitzungsebene ein Commit erfolgt.</span><span class="sxs-lookup"><span data-stu-id="887d8-114">If the block exits without an exception, the savepoint that was created for the block commits, but the transaction will not commit until the transaction at the session level commits.</span></span> <span data-ttu-id="887d8-115">Wenn der Block eine Ausnahme auslöst, wird für den ausgeführten Teil des Blocks ein Rollback ausgeführt, die Transaktion auf Sitzungsebene wird jedoch weiterhin ausgeführt, sofern die Ausnahme nicht zum Fehlschlagen der Transaktion führt.</span><span class="sxs-lookup"><span data-stu-id="887d8-115">If the block throws an exception, the effects of the block are rolled back but the transaction at the session level will proceed, unless the exception is transaction-dooming.</span></span> <span data-ttu-id="887d8-116">Beispielsweise kann ein Schreibkonflikt zum Fehlschlagen einer Transaktion führen, ein Typumwandlungsfehler jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="887d8-116">For example a write conflict is transaction-dooming, but not a type casting error.</span></span>  
  
 <span data-ttu-id="887d8-117">Wenn eine Sitzung keine aktive Transaktion enthält, wird durch `BEGIN ATOMIC` eine neue Transaktion gestartet.</span><span class="sxs-lookup"><span data-stu-id="887d8-117">If there is no active transaction on a session, `BEGIN ATOMIC` will start a new transaction.</span></span> <span data-ttu-id="887d8-118">Wenn außerhalb des Blockbereichs keine Ausnahme ausgelöst wird, wird für die Transaktion am Ende des Blocks ein Commit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="887d8-118">If no exception is thrown outside the scope of the block, the transaction will be committed at the end of the block.</span></span> <span data-ttu-id="887d8-119">Wenn der Block eine Ausnahme auslöst (d. h., die Ausnahme wird nicht innerhalb des Blocks abgefangen und behandelt), wird ein Rollback für die Transaktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="887d8-119">If the block throws an exception (that is, the exception is not caught and handled within the block), the transaction will be rolled back.</span></span> <span data-ttu-id="887d8-120">Bei Transaktionen, die einen einzelnen ATOMIC-Block (eine einzelne systemintern kompilierte gespeicherte Prozedur) umfassen, ist es nicht notwendig, explizite `BEGIN TRANSACTION`- und `COMMIT`- oder `ROLLBACK`-Anweisungen zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="887d8-120">For transactions that span a single atomic block (a single natively compiled stored procedure), you do not need to write explicit `BEGIN TRANSACTION` and `COMMIT` or `ROLLBACK` statements.</span></span>  
  
 <span data-ttu-id="887d8-121">Systemintern kompilierte gespeicherte Prozeduren unterstützen `TRY`-, `CATCH`- und `THROW`-Konstrukte zur Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="887d8-121">Natively compiled stored procedures support the `TRY`, `CATCH`, and `THROW` constructs for error handling.</span></span> <span data-ttu-id="887d8-122">`RAISERROR` wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="887d8-122">`RAISERROR` is not supported.</span></span>  
  
 <span data-ttu-id="887d8-123">Das folgende Beispiel veranschaulicht das Fehlerbehandlungsverhalten bei ATOMIC-Blöcken und systemintern kompilierten gespeicherten Prozeduren:</span><span class="sxs-lookup"><span data-stu-id="887d8-123">The following example illustrates the error handling behavior with atomic blocks and natively compiled stored procedures:</span></span>  
  
```sql  
-- sample table  
CREATE TABLE dbo.t1 (  
  c1 int not null primary key nonclustered  
)  
WITH (MEMORY_OPTIMIZED=ON)  
GO  
  
-- sample proc that inserts 2 rows  
CREATE PROCEDURE dbo.usp_t1 @v1 bigint not null, @v2 bigint not null  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS  
BEGIN ATOMIC  
WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english', DELAYED_DURABILITY = ON)  
  
  INSERT dbo.t1 VALUES (@v1)  
  INSERT dbo.t1 VALUES (@v2)  
  
END  
GO  
  
-- insert two rows  
EXEC dbo.usp_t1 1, 2  
GO  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify the rows 1 and 2 were committed  
SELECT c1 FROM dbo.t1  
GO  
  
-- execute proc with arithmetic overflow  
EXEC dbo.usp_t1 3, 4444444444444  
GO  
-- expected error message:  
-- Msg 8115, Level 16, State 0, Procedure usp_t1  
-- Arithmetic overflow error converting bigint to data type int.  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify rows 3 was not committed; usp_t1 has been rolled back  
SELECT c1 FROM dbo.t1  
GO  
  
-- start a new transaction  
BEGIN TRANSACTION  
  -- insert rows 3 and 4  
  EXEC dbo.usp_t1 3, 4  
  
  -- verify there is still an active transaction  
  SELECT @@TRANCOUNT  
  
  -- verify the rows 3 and 4 were inserted  
  SELECT c1 FROM dbo.t1 WITH (SNAPSHOT)   
  ORDER BY c1  
  
  -- catch the arithmetic overflow error  
  BEGIN TRY  
    EXEC dbo.usp_t1 5, 4444444444444  
  END TRY  
  BEGIN CATCH  
    PRINT N'Error occurred: ' + error_message()  
  END CATCH  
  
  -- verify there is still an active transaction  
  SELECT @@TRANCOUNT  
  
  -- verify rows 3 and 4 are still in the table, and row 5 has not been inserted  
  SELECT c1 FROM dbo.t1 WITH (SNAPSHOT)   
  ORDER BY c1  
  
COMMIT  
GO  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify rows 3 and 4 has been committed  
SELECT c1 FROM dbo.t1  
ORDER BY c1  
GO  
```  
  
 <span data-ttu-id="887d8-124">Bei folgenden, für speicheroptimierte Tabellen spezifischen Fehlern schlägt eine Transaktion fehl.</span><span class="sxs-lookup"><span data-stu-id="887d8-124">The following error messages specific to memory-optimized tables are transaction dooming.</span></span> <span data-ttu-id="887d8-125">Wenn sie im Bereich eines ATOMIC-Blocks auftreten, wird die Transaktion abgebrochen: 10772, 41301, 41302, 41305, 41325, 41332 und 41333.</span><span class="sxs-lookup"><span data-stu-id="887d8-125">If they occur in the scope of an atomic block, they will cause the transaction to abort: 10772, 41301, 41302, 41305, 41325, 41332, and 41333.</span></span>  
  
## <a name="session-settings"></a><span data-ttu-id="887d8-126">Sitzungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="887d8-126">Session Settings</span></span>  
 <span data-ttu-id="887d8-127">Die Sitzungseinstellungen in ATOMIC-Blöcken werden bei der Kompilierung der gespeicherte Prozedur fest definiert.</span><span class="sxs-lookup"><span data-stu-id="887d8-127">The session settings in atomic blocks are fixed when the stored procedure is compiled.</span></span> <span data-ttu-id="887d8-128">Einige Einstellungen können mit `BEGIN ATOMIC` angegeben werden, während andere immer denselben festen Wert aufweisen.</span><span class="sxs-lookup"><span data-stu-id="887d8-128">Some settings can be specified with `BEGIN ATOMIC` while other settings are always fixed to the same value.</span></span>  
  
 <span data-ttu-id="887d8-129">Die folgenden Optionen sind für `BEGIN ATOMIC` erforderlich:</span><span class="sxs-lookup"><span data-stu-id="887d8-129">The following options are required with `BEGIN ATOMIC`:</span></span>  
  
|<span data-ttu-id="887d8-130">Erforderliche Einstellung</span><span class="sxs-lookup"><span data-stu-id="887d8-130">Required Setting</span></span>|<span data-ttu-id="887d8-131">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="887d8-131">Description</span></span>|  
|----------------------|-----------------|  
|`TRANSACTION ISOLATION LEVEL`|<span data-ttu-id="887d8-132">Unterstützte Werte sind `SNAPSHOT`, `REPEATABLEREAD` und `SERIALIZABLE`.</span><span class="sxs-lookup"><span data-stu-id="887d8-132">Supported values are `SNAPSHOT`, `REPEATABLEREAD`, and `SERIALIZABLE`.</span></span>|  
|`LANGUAGE`|<span data-ttu-id="887d8-133">Bestimmt Datums- und Uhrzeitformate sowie Systemmeldungen.</span><span class="sxs-lookup"><span data-stu-id="887d8-133">Determines date and time formats and system messages.</span></span> <span data-ttu-id="887d8-134">Alle Sprachen und Aliase in [sys.syslanguages &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="887d8-134">All languages and aliases in [sys.syslanguages &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) are supported.</span></span>|  
  
 <span data-ttu-id="887d8-135">Die folgenden Einstellungen sind optional:</span><span class="sxs-lookup"><span data-stu-id="887d8-135">The following settings are optional:</span></span>  
  
|<span data-ttu-id="887d8-136">Optionale Einstellung</span><span class="sxs-lookup"><span data-stu-id="887d8-136">Optional Setting</span></span>|<span data-ttu-id="887d8-137">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="887d8-137">Description</span></span>|  
|----------------------|-----------------|  
|`DATEFORMAT`|<span data-ttu-id="887d8-138">Alle Datumsformate von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="887d8-138">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date formats are supported.</span></span> <span data-ttu-id="887d8-139">Falls angegeben, überschreibt `DATEFORMAT` das Standarddatumsformat, das `LANGUAGE` zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="887d8-139">When specified, `DATEFORMAT` overrides the default date format associated with `LANGUAGE`.</span></span>|  
|`DATEFIRST`|<span data-ttu-id="887d8-140">Falls angegeben, überschreibt `DATEFIRST` den Standardwert, der `LANGUAGE` zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="887d8-140">When specified, `DATEFIRST` overrides the default associated with `LANGUAGE`.</span></span>|  
|`DELAYED_DURABILITY`|<span data-ttu-id="887d8-141">Die Werte `OFF` und `ON` werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="887d8-141">Supported values are `OFF` and `ON`.</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="887d8-142">-Transaktionscommits können entweder vollständig dauerhaft (Standardeinstellung) oder verzögert dauerhaft sein. Weitere Informationen finden Sie unter [Steuern der Transaktionsdauerhaftigkeit](../logs/control-transaction-durability.md).</span><span class="sxs-lookup"><span data-stu-id="887d8-142">transaction commits can be either fully durable, the default, or delayed durable.For more information, see [Control Transaction Durability](../logs/control-transaction-durability.md).</span></span>|  
  
 <span data-ttu-id="887d8-143">Die folgenden SET-Optionen verfügen für alle ATOMIC-Blöcke in allen systemintern kompilierten gespeicherten Prozeduren über denselben Systemstandardwert:</span><span class="sxs-lookup"><span data-stu-id="887d8-143">The following SET options have the same system default value for all atomic blocks in all natively compiled stored procedures:</span></span>  
  
|<span data-ttu-id="887d8-144">SET-Option</span><span class="sxs-lookup"><span data-stu-id="887d8-144">Set Option</span></span>|<span data-ttu-id="887d8-145">Systemstandard für ATOMIC-Blöcke</span><span class="sxs-lookup"><span data-stu-id="887d8-145">System Default for Atomic Blocks</span></span>|  
|----------------|--------------------------------------|  
|<span data-ttu-id="887d8-146">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="887d8-146">ANSI_NULLS</span></span>|<span data-ttu-id="887d8-147">EIN</span><span class="sxs-lookup"><span data-stu-id="887d8-147">ON</span></span>|  
|<span data-ttu-id="887d8-148">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="887d8-148">ANSI_PADDING</span></span>|<span data-ttu-id="887d8-149">EIN</span><span class="sxs-lookup"><span data-stu-id="887d8-149">ON</span></span>|  
|<span data-ttu-id="887d8-150">ANSI_WARNING</span><span class="sxs-lookup"><span data-stu-id="887d8-150">ANSI_WARNING</span></span>|<span data-ttu-id="887d8-151">EIN</span><span class="sxs-lookup"><span data-stu-id="887d8-151">ON</span></span>|  
|<span data-ttu-id="887d8-152">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="887d8-152">ARITHABORT</span></span>|<span data-ttu-id="887d8-153">EIN</span><span class="sxs-lookup"><span data-stu-id="887d8-153">ON</span></span>|  
|<span data-ttu-id="887d8-154">ARITHIGNORE</span><span class="sxs-lookup"><span data-stu-id="887d8-154">ARITHIGNORE</span></span>|<span data-ttu-id="887d8-155">OFF</span><span class="sxs-lookup"><span data-stu-id="887d8-155">OFF</span></span>|  
|<span data-ttu-id="887d8-156">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="887d8-156">CONCAT_NULL_YIELDS_NULL</span></span>|<span data-ttu-id="887d8-157">EIN</span><span class="sxs-lookup"><span data-stu-id="887d8-157">ON</span></span>|  
|<span data-ttu-id="887d8-158">IDENTITY_INSERT</span><span class="sxs-lookup"><span data-stu-id="887d8-158">IDENTITY_INSERT</span></span>|<span data-ttu-id="887d8-159">OFF</span><span class="sxs-lookup"><span data-stu-id="887d8-159">OFF</span></span>|  
|<span data-ttu-id="887d8-160">NOCOUNT</span><span class="sxs-lookup"><span data-stu-id="887d8-160">NOCOUNT</span></span>|<span data-ttu-id="887d8-161">EIN</span><span class="sxs-lookup"><span data-stu-id="887d8-161">ON</span></span>|  
|<span data-ttu-id="887d8-162">NUMERIC_ROUNDABORT</span><span class="sxs-lookup"><span data-stu-id="887d8-162">NUMERIC_ROUNDABORT</span></span>|<span data-ttu-id="887d8-163">OFF</span><span class="sxs-lookup"><span data-stu-id="887d8-163">OFF</span></span>|  
|<span data-ttu-id="887d8-164">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="887d8-164">QUOTED_IDENTIFIER</span></span>|<span data-ttu-id="887d8-165">EIN</span><span class="sxs-lookup"><span data-stu-id="887d8-165">ON</span></span>|  
|<span data-ttu-id="887d8-166">ROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="887d8-166">ROWCOUNT</span></span>|<span data-ttu-id="887d8-167">0</span><span class="sxs-lookup"><span data-stu-id="887d8-167">0</span></span>|  
|<span data-ttu-id="887d8-168">TEXTSIZE</span><span class="sxs-lookup"><span data-stu-id="887d8-168">TEXTSIZE</span></span>|<span data-ttu-id="887d8-169">0</span><span class="sxs-lookup"><span data-stu-id="887d8-169">0</span></span>|  
|<span data-ttu-id="887d8-170">XACT_ABORT</span><span class="sxs-lookup"><span data-stu-id="887d8-170">XACT_ABORT</span></span>|<span data-ttu-id="887d8-171">OFF</span><span class="sxs-lookup"><span data-stu-id="887d8-171">OFF</span></span><br /><br /> <span data-ttu-id="887d8-172">Nicht abgefangene Ausnahmen bewirken ein Rollback für den ATOMIC-Block, führen jedoch nicht zu einem Abbruch der Transaktion, solange die Transaktion durch den Fehler nicht fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="887d8-172">Uncaught exceptions cause the atomic block to roll back, but not cause the transaction to abort unless the error is transaction dooming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="887d8-173">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="887d8-173">See Also</span></span>  
 [<span data-ttu-id="887d8-174">Nativ kompilierte gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="887d8-174">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
