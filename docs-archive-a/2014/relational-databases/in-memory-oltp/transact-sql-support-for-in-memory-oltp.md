---
title: Transact-SQL-Unterstützung für In-Memory OLTP | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: b1cc7c30-1747-4c21-88ac-e95a5e58baac
author: rothja
ms.author: jroth
ms.openlocfilehash: bf3708a258e3bb97231e45b10bea2c59351a06a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724657"
---
# <a name="transact-sql-support-for-in-memory-oltp"></a><span data-ttu-id="445f8-102">Transact-SQL-Unterstützung für In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="445f8-102">Transact-SQL Support for In-Memory OLTP</span></span>
  <span data-ttu-id="445f8-103">Der Zugriff auf speicheroptimierte Tabellen ist über beliebige Transact-SQL-Abfragen oder DML-Anweisungen (SELECT, INSERT, UPDATE oder DELETE), Ad-hoc-Anweisungen sowie über SQL-Module wie gespeicherte Prozeduren, Tabellenwertfunktionen, Skalarfunktionen, Trigger und Sichten möglich.</span><span class="sxs-lookup"><span data-stu-id="445f8-103">You can access memory-optimized tables using any Transact-SQL query or DML statement (SELECT, INSERT, UPDATE, or DELETE), ad hoc statement, and SQL module such as stored procedures, table-value functions, scalar functions, triggers, and views.</span></span> <span data-ttu-id="445f8-104">Weitere Informationen finden [Sie unter Zugreifen auf Speicher optimierte Tabellen mit interpretiertem Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="445f8-104">For more information see [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span></span>  
  
 <span data-ttu-id="445f8-105">Gespeicherte Prozeduren, die nur auf speicheroptimierte Tabellen verweisen, können systemintern in Computercode kompiliert werden. Dies bietet in der Regel großen Leistungszuwachs über interpretierte (datenträgerbasierte) gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="445f8-105">Stored procedures that only reference memory-optimized tables can be natively compiled into machine code and typically provide significant performance gains over interpreted (disk-based) stored procedures.</span></span> <span data-ttu-id="445f8-106">Verwenden Sie für einen optimalen Zugriff auf die speicheroptimierten Tabellen die systemintern kompilierten gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="445f8-106">For optimized access to memory-optimized tables use natively compiled stored procedures.</span></span> <span data-ttu-id="445f8-107">Weitere Informationen finden Sie unter [Nativ kompilierte gespeicherte Prozeduren](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="445f8-107">For more information, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="445f8-108">Beim Erstellen oder Ändern von Datenbankobjekten (DDL-Anweisungen) wurden die folgenden Anweisungen geändert:</span><span class="sxs-lookup"><span data-stu-id="445f8-108">When creating and modifying database objects (DDL statements), the following statements have been modified:</span></span>  
  
-   <span data-ttu-id="445f8-109">[ALTER DATABASE-Optionen für Dateien und Dateigruppen &#40;Transact-SQL-&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) (siehe `MEMORY_OPTIMIZED_DATA` )</span><span class="sxs-lookup"><span data-stu-id="445f8-109">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) (see `MEMORY_OPTIMIZED_DATA`)</span></span>  
  
-   <span data-ttu-id="445f8-110">[Create Database &#40;SQL Server Transact-SQL-&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) (siehe `MEMORY_OPTIMIZED_DATA` )</span><span class="sxs-lookup"><span data-stu-id="445f8-110">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) (see `MEMORY_OPTIMIZED_DATA`)</span></span>  
  
-   <span data-ttu-id="445f8-111">[CREATE PROCEDURE &#40;Transact-SQL-&#41;](/sql/t-sql/statements/create-procedure-transact-sql) (siehe `NATIVE_COMPILATION` , `SCHEMABINDING` , `EXECUTE AS` und `BEGIN ATOMIC` )</span><span class="sxs-lookup"><span data-stu-id="445f8-111">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) (see `NATIVE_COMPILATION`, `SCHEMABINDING`, `EXECUTE AS`, and `BEGIN ATOMIC`)</span></span>  
  
-   <span data-ttu-id="445f8-112">[CREATE TABLE &#40;Transact-SQL-&#41;](/sql/t-sql/statements/create-table-transact-sql) (siehe `MEMORY_OPTIMIZED` ,, `DURABILITY` `BUCKET_COUNT` , `INDEX` und `HASH` )</span><span class="sxs-lookup"><span data-stu-id="445f8-112">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) (see `MEMORY_OPTIMIZED`, `DURABILITY`, `BUCKET_COUNT`, `INDEX`, and `HASH`)</span></span>  
  
-   <span data-ttu-id="445f8-113">[Create Type &#40;Transact-SQL-&#41;](/sql/t-sql/statements/create-type-transact-sql) (siehe `MEMORY_OPTIMIZED` , `BUCKET_COUNT` , `INDEX` und `HASH` )</span><span class="sxs-lookup"><span data-stu-id="445f8-113">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) (see `MEMORY_OPTIMIZED`, `BUCKET_COUNT`, `INDEX`, and `HASH`)</span></span>  
  
-   <span data-ttu-id="445f8-114">[Deklarieren @local_variable &#40;Transact-SQL-&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) (siehe `NULL`  |  `NOT NULL` )</span><span class="sxs-lookup"><span data-stu-id="445f8-114">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) (see `NULL` | `NOT NULL`)</span></span>  
  
 <span data-ttu-id="445f8-115">Speicheroptimierte Tabelle unterstützen `PRIMARY KEY`- und `NOT NULL`-Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="445f8-115">Memory-optimized tables support `PRIMARY KEY` and `NOT NULL` constraints.</span></span> <span data-ttu-id="445f8-116">Informationen zum Implementieren von nicht unterstützten Einschränkungen finden [Sie unter Migrieren von Check-und FOREIGN KEY-Einschränkungen](../../database-engine/migrating-check-and-foreign-key-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="445f8-116">For information on implementing unsupported constraints, see [Migrating Check and Foreign Key Constraints](../../database-engine/migrating-check-and-foreign-key-constraints.md).</span></span>  
  
 <span data-ttu-id="445f8-117">Informationen zu nicht unterstützten Funktionen finden Sie unter [Von In-Memory-OLTP nicht unterstützte Transact-SQL-Konstrukte](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="445f8-117">For information on unsupported features, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="445f8-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="445f8-118">In This Section</span></span>  
  
-   [<span data-ttu-id="445f8-119">Unterstützte Datentypen</span><span class="sxs-lookup"><span data-stu-id="445f8-119">Supported Data Types</span></span>](supported-data-types-for-in-memory-oltp.md)  
  
-   [<span data-ttu-id="445f8-120">Zugreifen auf speicheroptimierte Tabellen mit interpretiertem Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="445f8-120">Accessing Memory-Optimized Tables Using Interpreted Transact-SQL</span></span>](accessing-memory-optimized-tables-using-interpreted-transact-sql.md)  
  
-   [<span data-ttu-id="445f8-121">Systemsichten, gespeicherte Prozeduren, DMVs und Wartetypen für In-Memory-OLTP</span><span class="sxs-lookup"><span data-stu-id="445f8-121">System Views, Stored Procedures, DMVs and Wait Types for In-Memory OLTP</span></span>](../../database-engine/system-views-stored-procedures-dmvs-and-wait-types-for-in-memory-oltp.md)  
  
## <a name="see-also"></a><span data-ttu-id="445f8-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="445f8-122">See Also</span></span>  
 <span data-ttu-id="445f8-123">[In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="445f8-123">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 <span data-ttu-id="445f8-124">[Migrationsprobleme bei systemintern kompilierten gespeicherten Prozeduren](migration-issues-for-natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="445f8-124">[Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md) </span></span>  
 <span data-ttu-id="445f8-125">[Unterstützte SQL Server Features](unsupported-sql-server-features-for-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="445f8-125">[Supported SQL Server Features](unsupported-sql-server-features-for-in-memory-oltp.md) </span></span>  
 [<span data-ttu-id="445f8-126">Nativ kompilierte gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="445f8-126">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
