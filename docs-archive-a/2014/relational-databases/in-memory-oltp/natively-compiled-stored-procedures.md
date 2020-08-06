---
title: Systemintern kompilierte gespeicherte Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
helpviewer_keywords:
- natively compiled stored procedures
ms.assetid: d5ed432c-10c5-4e4f-883c-ef4d1fa32366
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b8fb7a379c0c08ca357baa1042ebcf51c512c9ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722814"
---
# <a name="natively-compiled-stored-procedures"></a><span data-ttu-id="0ec27-102">Systemintern kompilierte gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0ec27-102">Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="0ec27-103">Systemintern kompilierte gespeicherte Prozeduren sind gespeicherte [!INCLUDE[tsql](../../includes/tsql-md.md)] -Prozeduren, die in systemeigenen Code kompiliert werden und auf speicheroptimierte Tabellen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0ec27-103">Natively compiled stored procedures are [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures compiled to native code that access memory-optimized tables.</span></span> <span data-ttu-id="0ec27-104">Systemintern kompilierte gespeicherte Prozeduren ermöglichen die effiziente Ausführung der Abfragen und Geschäftslogik in der gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0ec27-104">Natively compiled stored procedures allow for efficient execution of queries and business logic in the stored procedure.</span></span> <span data-ttu-id="0ec27-105">Ausführliche Informationen zur systeminternen Kompilierung finden Sie unter [Native Compilation of Tables and Stored Procedures](native-compilation-of-tables-and-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="0ec27-105">For more details about the native compilation process, see [Native Compilation of Tables and Stored Procedures](native-compilation-of-tables-and-stored-procedures.md).</span></span> <span data-ttu-id="0ec27-106">Weitere Informationen zum Migrieren von datenträgerbasierten gespeicherten Prozeduren zu nativ kompilierten gespeicherten Prozeduren finden Sie unter [Migrationsprobleme bei nativ kompilierten gespeicherten Prozeduren](migration-issues-for-natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="0ec27-106">For more information about migrating disk-based stored procedures to natively compiled stored procedures, see [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ec27-107">Ein Unterschied zwischen interpretierten (datenträgerbasierten) gespeicherten Prozeduren und systemintern kompilierten gespeicherten Prozeduren besteht darin, dass eine interpretierte gespeicherte Prozedur bei der ersten Ausführung kompiliert wird, während eine systemintern kompilierte gespeicherte Prozedur bei der Erstellung kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="0ec27-107">One difference between interpreted (disk-based) stored procedures and natively compiled stored procedures is that an interpreted stored procedure is compiled at first execution whereas a natively compiled stored procedure is compiled when it is created.</span></span> <span data-ttu-id="0ec27-108">Bei systemintern kompilierten gespeicherten Prozeduren können viele Fehlerbedingungen (arithmetischer Überlauf, Typkonvertierung und bestimmte Bedingungen bei Division durch null) bei der Erstellung festgestellt werden, die zu einem Fehler bei der Erstellung der systemintern kompilierten gespeicherten Prozedur führen.</span><span class="sxs-lookup"><span data-stu-id="0ec27-108">With natively compiled stored procedures, many error conditions (arithmetic overflow, type conversion, and some divide-by-zero conditions) can be detected at create time and will cause creation of the natively compiled stored procedure to fail.</span></span> <span data-ttu-id="0ec27-109">Bei interpretierten gespeicherten Prozeduren führen diese Fehlerbedingungen in der Regel zu keinem Fehler, wenn die gespeicherte Prozedur erstellt wird, sondern bei jeder Ausführung.</span><span class="sxs-lookup"><span data-stu-id="0ec27-109">With interpreted stored procedures, these error conditions will typically not cause a failure when the stored procedure is created, but all executions will fail.</span></span>  
  
 <span data-ttu-id="0ec27-110">Themen in diesem Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="0ec27-110">Topics in this section:</span></span>  
  
-   [<span data-ttu-id="0ec27-111">Erstellen systemintern kompilierter gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0ec27-111">Creating Natively Compiled Stored Procedures</span></span>](creating-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="0ec27-112">Atomic-Blöcke</span><span class="sxs-lookup"><span data-stu-id="0ec27-112">Atomic Blocks</span></span>](atomic-blocks-in-native-procedures.md)  
  
-   [<span data-ttu-id="0ec27-113">Unterstützte Konstrukte in nativ kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0ec27-113">Supported Constructs in Natively Compiled Stored Procedures</span></span>](supported-features-for-natively-compiled-t-sql-modules.md)  
  
-   [<span data-ttu-id="0ec27-114">Verwenden von TRY...CATCH in nativ kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0ec27-114">Using Try..Catch in Natively Compiled Stored Procedures</span></span>](../../database-engine/using-try-catch-in-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="0ec27-115">Unterstützte Konstrukte für nativ kompilierte gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0ec27-115">Supported Constructs on Natively Compiled Stored Procedures</span></span>](supported-ddl-for-natively-compiled-t-sql-modules.md)  
  
-   [<span data-ttu-id="0ec27-116">Systemintern kompilierte gespeicherte Prozeduren und deren Ausführung mit SET-Optionen</span><span class="sxs-lookup"><span data-stu-id="0ec27-116">Natively Compiled Stored Procedures and Execution Set Options</span></span>](natively-compiled-stored-procedures-and-execution-set-options.md)  
  
-   [<span data-ttu-id="0ec27-117">Bewährte Vorgehensweisen für den Aufruf von systemintern kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0ec27-117">Best Practices for Calling Natively Compiled Stored Procedures</span></span>](best-practices-for-calling-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="0ec27-118">Überwachen der Leistung von systemintern kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0ec27-118">Monitoring Performance of Natively Compiled Stored Procedures</span></span>](monitoring-performance-of-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="0ec27-119">Aufrufen von systemintern kompilierten gespeicherten Prozeduren über Datenzugriffsanwendungen</span><span class="sxs-lookup"><span data-stu-id="0ec27-119">Calling Natively Compiled Stored Procedures from Data Access Applications</span></span>](calling-natively-compiled-stored-procedures-from-data-access-applications.md)  
  
## <a name="see-also"></a><span data-ttu-id="0ec27-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ec27-120">See Also</span></span>  
 [<span data-ttu-id="0ec27-121">Speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="0ec27-121">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
