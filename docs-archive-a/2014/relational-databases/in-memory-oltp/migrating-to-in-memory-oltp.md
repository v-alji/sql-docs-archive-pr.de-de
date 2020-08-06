---
title: Migration zu In-Memory OLTP | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 405cdac5-a0d4-47a4-9180-82876b773b82
author: rothja
ms.author: jroth
ms.openlocfilehash: ed764ce52d41d76667213b846cec51b26f634a27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725773"
---
# <a name="migrating-to-in-memory-oltp"></a><span data-ttu-id="5b270-102">Migrating to In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="5b270-102">Migrating to In-Memory OLTP</span></span>
  <span data-ttu-id="5b270-103">In diesem Abschnitt wird erläutert, wie Datenbankobjekte für die Verwendung von In-Memory OLTP migriert werden.</span><span class="sxs-lookup"><span data-stu-id="5b270-103">This section discusses how to migrate database objects to use In-Memory OLTP.</span></span>  
  
-   [<span data-ttu-id="5b270-104">Bestimmen, ob eine Tabelle oder eine gespeicherte Prozedur zu In-Memory-OLTP portiert werden soll</span><span class="sxs-lookup"><span data-stu-id="5b270-104">Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP</span></span>](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)  
  
-   [<span data-ttu-id="5b270-105">Advisor für die Speicheroptimierung</span><span class="sxs-lookup"><span data-stu-id="5b270-105">Memory Optimization Advisor</span></span>](memory-optimization-advisor.md)  
  
-   [<span data-ttu-id="5b270-106">Ratgeber für native Kompilierung</span><span class="sxs-lookup"><span data-stu-id="5b270-106">Native Compilation Advisor</span></span>](native-compilation-advisor.md)  
  
-   [<span data-ttu-id="5b270-107">Von In-Memory OLTP nicht unterstützte Transact-SQL-Konstrukte.</span><span class="sxs-lookup"><span data-stu-id="5b270-107">Transact-SQL Constructs Not Supported by In-Memory OLTP</span></span>](transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
-   [<span data-ttu-id="5b270-108">Implementieren von LOB-Spalten in einer speicheroptimierten Tabelle</span><span class="sxs-lookup"><span data-stu-id="5b270-108">Implementing LOB Columns in a Memory-Optimized Table</span></span>](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md)  
  
-   [<span data-ttu-id="5b270-109">Implementieren von SQL_VARIANT in einer speicheroptimierten Tabelle</span><span class="sxs-lookup"><span data-stu-id="5b270-109">Implementing SQL_VARIANT in a Memory-Optimized Table</span></span>](implementing-sql-variant-in-a-memory-optimized-table.md)  
  
-   [<span data-ttu-id="5b270-110">Migrationsprobleme bei nativ kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="5b270-110">Migration Issues for Natively Compiled Stored Procedures</span></span>](migration-issues-for-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="5b270-111">Migrieren von berechneten Spalten</span><span class="sxs-lookup"><span data-stu-id="5b270-111">Migrating Computed Columns</span></span>](migrating-computed-columns.md)  
  
-   [<span data-ttu-id="5b270-112">Migrieren von Triggern</span><span class="sxs-lookup"><span data-stu-id="5b270-112">Migrating Triggers</span></span>](migrating-triggers.md)  
  
-   [<span data-ttu-id="5b270-113">Datenbankübergreifende Abfragen</span><span class="sxs-lookup"><span data-stu-id="5b270-113">Cross-Database Queries</span></span>](cross-database-queries.md)  
  
-   [<span data-ttu-id="5b270-114">Migrieren von Überprüfungs- und Fremdschlüsseleinschränkungen</span><span class="sxs-lookup"><span data-stu-id="5b270-114">Migrating Check and Foreign Key Constraints</span></span>](../../database-engine/migrating-check-and-foreign-key-constraints.md)  
  
-   [<span data-ttu-id="5b270-115">Implementieren von IDENTITY in einer speicheroptimierten Tabelle</span><span class="sxs-lookup"><span data-stu-id="5b270-115">Implementing IDENTITY in a Memory-Optimized Table</span></span>](implementing-identity-in-a-memory-optimized-table.md)  
  
 <span data-ttu-id="5b270-116">Weitere Informationen zu Migrationsmethoden finden Sie unter [In-Memory OLTP - Common Workload Patterns and Migration Considerations (In-Memory-OLTP: Allgemeine Workloadmuster und Überlegungen zur Migration)](https://msdn.microsoft.com/library/dn673538.aspx).</span><span class="sxs-lookup"><span data-stu-id="5b270-116">For information about migration methodologies, see [In-Memory OLTP - Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b270-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b270-117">See Also</span></span>  
 <span data-ttu-id="5b270-118">[In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="5b270-118">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 [<span data-ttu-id="5b270-119">Schätzen der Arbeitsspeicheranforderungen speicheroptimierter Tabellen</span><span class="sxs-lookup"><span data-stu-id="5b270-119">Estimate Memory Requirements for Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
