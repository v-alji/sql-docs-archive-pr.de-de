---
title: Grundlegendes zu Transaktionen in Speicher optimierten Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 06075248-705e-4563-9371-b64cd609793c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0671bba8b7a0bda27ea27cf059cb9e3b1bb87b2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701523"
---
# <a name="understanding-transactions-on-memory-optimized-tables"></a><span data-ttu-id="140aa-102">Grundlegendes zu Transaktionen in speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="140aa-102">Understanding Transactions on Memory-Optimized Tables</span></span>
  <span data-ttu-id="140aa-103">Transaktionen greifen über eine Form der Multiversionsverwaltung und optimistischen Nebenläufigkeitssteuerung auf speicheroptimierte Tabellen zu.</span><span class="sxs-lookup"><span data-stu-id="140aa-103">Transactions access memory-optimized tables using a form of optimistic, multi-version concurrency control.</span></span> <span data-ttu-id="140aa-104">Dies bedeutet, dass es zwei verschiedene Datenversionen gibt.</span><span class="sxs-lookup"><span data-stu-id="140aa-104">This means that there are different versions of the data.</span></span> <span data-ttu-id="140aa-105">Jede Transaktion verwendet ihre eigene, im Hinblick auf Transaktionen konsistente Datenbankversion, und zwar unabhängig von anderen gleichzeitig ausgeführten Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="140aa-105">Each transaction operates on its own transactionally consistent version of the database, independent from other concurrently running transactions.</span></span> <span data-ttu-id="140aa-106">Darüber hinaus werden Transaktionen unter der optimistischen Annahme ausgeführt, dass keine Konflikte mit anderen, gleichzeitig laufenden Transaktionen bestehen.</span><span class="sxs-lookup"><span data-stu-id="140aa-106">In addition, transactions operate under the optimistic assumption that there will be no conflicts with other, concurrent, transactions.</span></span> <span data-ttu-id="140aa-107">Einerseits entfällt dadurch die Notwendigkeit von Sperren, andererseits muss das System die Konflikte erkennen und eine der konfliktverursachenden Transaktionen beenden.</span><span class="sxs-lookup"><span data-stu-id="140aa-107">This avoids the need to use locks, but does require the system to detect conflicts and terminate one of the conflicting transactions.</span></span> <span data-ttu-id="140aa-108">Konflikte können nur bei Write-Write-Transaktionen und Read-Write-Transaktionen auftreten.</span><span class="sxs-lookup"><span data-stu-id="140aa-108">Conflicts can occur only for write-write transactions and for read-write transactions.</span></span> <span data-ttu-id="140aa-109">Wenn ein Write-Write-Konflikt auftritt, wird eine Schreibtransaktion beendet.</span><span class="sxs-lookup"><span data-stu-id="140aa-109">If there is a write-write conflict, one write transaction is terminated.</span></span>  
  
 <span data-ttu-id="140aa-110">Es gibt Ähnlichkeiten zwischen der Parallelitätssteuerung für speicheroptimierte Tabellen und der Parallelitätssteuerung für datenträgerbasierte Tabellen mit der Transaktionsisolationsstufe READ_COMMITTED_SNAPSHOT oder SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="140aa-110">There are similarities between the concurrency control for memory-optimized tables and the concurrency control for disk-based tables for the READ_COMMITTED_SNAPSHOT and SNAPSHOT transaction isolation levels.</span></span> <span data-ttu-id="140aa-111">(Weitere Informationen zu Datenträger basierten Tabellen finden Sie unter auf [Zeilen Versionsverwaltung basierende Isolations Stufen in der Datenbank-Engine](https://msdn.microsoft.com/library/ms177404\(v=sql.100\).aspx).)</span><span class="sxs-lookup"><span data-stu-id="140aa-111">(For more information about disk-based tables, see [Row Versioning-based Isolation Levels in the Database Engine](https://msdn.microsoft.com/library/ms177404\(v=sql.100\).aspx).)</span></span>  
  
## <a name="topics-in-this-section"></a><span data-ttu-id="140aa-112">Themen in diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="140aa-112">Topics in This Section</span></span>  
 <span data-ttu-id="140aa-113">Dieser Abschnitt über Transaktionen in speicheroptimierten Tabellen enthält folgende Themen:</span><span class="sxs-lookup"><span data-stu-id="140aa-113">This section on transactions in memory-optimized tables includes the following topics:</span></span>  
  
-   [<span data-ttu-id="140aa-114">Richtlinien für Transaktionsisolationsstufen mit speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="140aa-114">Guidelines for Transaction Isolation Levels with Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
-   [<span data-ttu-id="140aa-115">Richtlinien zur Wiederholungslogik für Transaktionen auf speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="140aa-115">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>](guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="140aa-116">Transaktionen in speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="140aa-116">Transactions in Memory-Optimized Tables</span></span>](transactions-in-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="140aa-117">Transaktionsisolationsstufen</span><span class="sxs-lookup"><span data-stu-id="140aa-117">Transaction Isolation Levels</span></span>](transaction-isolation-levels.md)  
  
-   [<span data-ttu-id="140aa-118">Containerübergreifende Transaktionen</span><span class="sxs-lookup"><span data-stu-id="140aa-118">Cross-Container Transactions</span></span>](cross-container-transactions.md)  
  
 <span data-ttu-id="140aa-119">Weitere Informationen finden Sie im Thema [Steuern der Transaktionsdauerhaftigkeit](../relational-databases/logs/control-transaction-durability.md).</span><span class="sxs-lookup"><span data-stu-id="140aa-119">For more information, see [Control Transaction Durability](../relational-databases/logs/control-transaction-durability.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="140aa-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="140aa-120">See Also</span></span>  
 [<span data-ttu-id="140aa-121">Speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="140aa-121">Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
  
