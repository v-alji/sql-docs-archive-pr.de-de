---
title: Speicheroptimierte Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 14dddf81-b502-49dc-a6b6-d18b1ae32d2b
author: rothja
ms.author: jroth
ms.openlocfilehash: 73430505e55230daf31c492d882eadeb6d35d29f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724678"
---
# <a name="memory-optimized-tables"></a><span data-ttu-id="3e641-102">Speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="3e641-102">Memory-Optimized Tables</span></span>
  <span data-ttu-id="3e641-103">Mit[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] In-Memory OLTP wird die Leistung von OLTP-Anwendungen durch effiziente, speicheroptimierte Datenzugriffe, systeminterne Kompilierung der Geschäftslogik sowie sperr- und latchfreie Algorithmen verbessert.</span><span class="sxs-lookup"><span data-stu-id="3e641-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] In-Memory OLTP helps improve performance of OLTP applications through efficient, memory-optimized data access, native compilation of business logic, and lock- and latch free algorithms.</span></span> <span data-ttu-id="3e641-104">Die In-Memory OLTP-Funktion enthält speicheroptimierte Tabellen und Tabellentypen sowie systeminterne Kompilierung von gespeicherten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Prozeduren für effizienten Zugriff auf diese Tabellen.</span><span class="sxs-lookup"><span data-stu-id="3e641-104">The In-Memory OLTP feature includes memory-optimized tables and table types, as well as native compilation of [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures for efficient access to these tables.</span></span>  
  
 <span data-ttu-id="3e641-105">Weitere Informationen zu speicheroptimierten Tabellen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="3e641-105">For more information about memory-optimized tables, see:</span></span>  
  
-   [<span data-ttu-id="3e641-106">Einführung in speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="3e641-106">Introduction to Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
     <span data-ttu-id="3e641-107">Erläutert, was speicheroptimierte Tabellen sind, und stellt Informationen über die Dauerhaftigkeit von Daten, den Zugriff auf Daten in speicheroptimierten Tabellen und die Leistung sowie Skalierbarkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="3e641-107">Details what memory-optimized tables are and provides information about data durability, accessing data in memory-optimized tables, and performance and scalability.</span></span>  
  
-   [<span data-ttu-id="3e641-108">Systeminterne Kompilierung von Tabellen und gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="3e641-108">Native Compilation of Tables and Stored Procedures</span></span>](../in-memory-oltp/natively-compiled-stored-procedures.md)  
  
     <span data-ttu-id="3e641-109">Erläutert, wie speicheroptimierte Tabellen und systemintern kompilierten gespeicherten Prozeduren in DLLs kompiliert werden, und stellt Sicherheitsüberlegungen in diesem Zusammenhang dar.</span><span class="sxs-lookup"><span data-stu-id="3e641-109">Details how memory-optimized tables and natively compiled stored procedures are compiled into DLLs, and provides related security considerations.</span></span>  
  
-   [<span data-ttu-id="3e641-110">Ändern von speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="3e641-110">Altering Memory-Optimized Tables</span></span>](altering-memory-optimized-tables.md)  
  
     <span data-ttu-id="3e641-111">Richtlinien für die Aktualisierung von speicheroptimierten Tabellen (einschließlich dem Ändern von Tabellenspalten, Indizes und bucket_count).</span><span class="sxs-lookup"><span data-stu-id="3e641-111">Guidelines for updating memory-optimized tables (including changing table columns, indexes, and bucket_count).</span></span>  
  
-   [<span data-ttu-id="3e641-112">Grundlegendes zu Transaktionen in speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="3e641-112">Understanding Transactions on Memory-Optimized Tables</span></span>](../../database-engine/understanding-transactions-on-memory-optimized-tables.md)  
  
     <span data-ttu-id="3e641-113">Dieser Abschnitt enthält mehrere Themen in Bezug auf die Durchführung von Transaktionen in speicheroptimierten Tabellen, einschließlich Transaktionsisolationsstufen und containerübergreifenden Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="3e641-113">This section provides several topics related to performing transactions on memory-optimized tables including transaction isolation levels, and cross-container transactions.</span></span>  
  
-   [<span data-ttu-id="3e641-114">Anwendungsmuster zur Partitionierung von speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="3e641-114">Application Pattern for Partitioning Memory-Optimized Tables</span></span>](application-pattern-for-partitioning-memory-optimized-tables.md)  
  
     <span data-ttu-id="3e641-115">Detailliertes Codebeispiel, das darstellt, wie partitionierte Tabellen bei der Verwendung von speicheroptimierten Tabellen emuliert werden.</span><span class="sxs-lookup"><span data-stu-id="3e641-115">Detailed code sample that shows how to emulate partitioned tables when using memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="3e641-116">Statistiken für speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="3e641-116">Statistics for Memory-Optimized Tables</span></span>](statistics-for-memory-optimized-tables.md)  
  
     <span data-ttu-id="3e641-117">Erläutert, wie Statistiken für speicheroptimierte Tabellen kompiliert werden und wie diese Statistiken gepflegt und manuell aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3e641-117">Details how statistics are compiled for memory-optimized tables and how to maintain and manually update statistics for memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="3e641-118">Sortierungen und Codepages</span><span class="sxs-lookup"><span data-stu-id="3e641-118">Collations and Code Pages</span></span>](../../database-engine/collations-and-code-pages.md)  
  
     <span data-ttu-id="3e641-119">Erläutert die Einschränkungen für unterstützte Sortierungen und Codeseiten für speicheroptimierte Tabellen.</span><span class="sxs-lookup"><span data-stu-id="3e641-119">Details the restrictions on supported collations and code pages for memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="3e641-120">Tabellen- und Zeilengröße in speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="3e641-120">Table and Row Size in Memory-Optimized Tables</span></span>](table-and-row-size-in-memory-optimized-tables.md)  
  
     <span data-ttu-id="3e641-121">Erläutert den Grenzwert von 8.060 Byte in den Zeilen speicheroptimierter Tabellen, und gibt ein Beispiel für die Berechnung von Tabellen- und Zeilengrößen an.</span><span class="sxs-lookup"><span data-stu-id="3e641-121">Details the 8060 byte limit on memory-optimized table rows, and provides an example for calculating table and row sizes.</span></span>  
  
-   [<span data-ttu-id="3e641-122">Anleitung zur Abfrageverarbeitung für speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="3e641-122">A Guide to Query Processing for Memory-Optimized Tables</span></span>](a-guide-to-query-processing-for-memory-optimized-tables.md)  
  
     <span data-ttu-id="3e641-123">Gibt eine Übersicht über die Abfrageverarbeitung für speicheroptimierte Tabellen und systemintern kompilierte gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="3e641-123">Provides an overview of query processing for both memory-optimized tables, and natively compiled stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e641-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e641-124">See Also</span></span>  
 [<span data-ttu-id="3e641-125">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="3e641-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp-in-memory-optimization.md)  
  
  
