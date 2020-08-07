---
title: Systeminterne Kompilierung von Tabellen und gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5880fbd9-a23e-464a-8b44-09750eeb2dad
author: rothja
ms.author: jroth
ms.openlocfilehash: 32c5b04610d894e06278fbeecdaf3bbebe850d60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619119"
---
# <a name="native-compilation-of-tables-and-stored-procedures"></a><span data-ttu-id="5e3b7-102">Systeminterne Kompilierung von Tabellen und gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="5e3b7-102">Native Compilation of Tables and Stored Procedures</span></span>
  <span data-ttu-id="5e3b7-103">Mit In-Memory OLTP wird das Konzept der systeminternen Kompilierung eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-103">In-Memory OLTP introduces the concept of native compilation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5e3b7-104">kann gespeicherte Prozeduren, die auf speicheroptimierte Tabellen zugreifen, nativ kompilieren.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-104">can natively compile stored procedures that access memory-optimized tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5e3b7-105">kann außerdem speicheroptimierte Tabellen nativ kompilieren.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-105">is also able to natively compile memory-optimized tables.</span></span> <span data-ttu-id="5e3b7-106">Die systeminterne Kompilierung ermöglicht einen schnelleren Datenzugriff und eine effizientere Abfrageausführung als interpretiertes (herkömmliches) [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e3b7-106">Native compilation allows faster data access and more efficient query execution than interpreted (traditional) [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5e3b7-107">Beim systeminternen Kompilieren von Tabellen und gespeicherten Prozeduren werden DLLs erzeugt.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-107">Native compilation of tables and stored procedures produce DLLs.</span></span>  
  
 <span data-ttu-id="5e3b7-108">Die systeminterne Kompilierung von speicheroptimierten Tabellentypen wird ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-108">Native compilation of memory optimized table types is also supported.</span></span> <span data-ttu-id="5e3b7-109">Weitere Informationen finden Sie unter [Memory-Optimized Table Variables](../../database-engine/memory-optimized-table-variables.md).</span><span class="sxs-lookup"><span data-stu-id="5e3b7-109">For more information, see [Memory-Optimized Table Variables](../../database-engine/memory-optimized-table-variables.md).</span></span>  
  
 <span data-ttu-id="5e3b7-110">Systeminterne Kompilierung bezieht sich auf den Prozess der Konvertierung von Programmkonstrukten in systemeigenen Code, der aus Prozessoranweisungen besteht, die keine weitere Kompilierung oder Interpretation erfordern.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-110">Native compilation refers to the process of converting programming constructs to native code, consisting of processor instructions without the need for further compilation or interpretation.</span></span>  
  
 <span data-ttu-id="5e3b7-111">In-Memory OLTP kompiliert speicheroptimierte Tabellen bei deren Erstellung sowie systemintern kompilierte gespeicherte Prozeduren beim Laden in systemeigene DLLs.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-111">In-Memory OLTP compiles memory-optimized tables when they are created, and natively compiled stored procedures when they are loaded to native DLLs.</span></span> <span data-ttu-id="5e3b7-112">Außerdem werden die DLLs nach einem Datenbank- oder Serverneustart neu kompiliert.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-112">In addition, the DLLs are recompiled after a database or server restart.</span></span> <span data-ttu-id="5e3b7-113">Die zum erneuten Erstellen der DLLs erforderlichen Informationen werden in den Datenbankmetadaten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-113">The information necessary to recreate the DLLs is stored in the database metadata.</span></span> <span data-ttu-id="5e3b7-114">Die DLLs sind nicht Teil der Datenbank, sie sind der Datenbank aber zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-114">The DLLs are not part of the database, though they are associated with the database.</span></span> <span data-ttu-id="5e3b7-115">Beispielsweise sind die DLLs nicht in den Datenbanksicherungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-115">For example, the DLLs are not included in database backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e3b7-116">Speicheroptimierte Tabellen werden beim jedem Serverneustart neu kompiliert.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-116">Memory-optimized tables are recompiled during a server restart.</span></span> <span data-ttu-id="5e3b7-117">Um die Datenbankwiederherstellung zu beschleunigen, werden systemintern kompilierte gespeicherte Prozeduren beim Serverneustart nicht neu kompiliert. Sie werden stattdessen bei der ersten Ausführung kompiliert.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-117">To speed up database recovery, natively compiled stored procedures are not recompiled during a server restart, they are compiled at the time of first execution.</span></span> <span data-ttu-id="5e3b7-118">Aufgrund dieser verzögerten Kompilierung werden systemintern kompilierte gespeicherte Prozeduren erst dann angezeigt, wenn [sys.dm_os_loaded_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-loaded-modules-transact-sql) nach der ersten Ausführung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-118">As a result of this deferred compilation, natively compiled stored procedures only appear when calling [sys.dm_os_loaded_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-loaded-modules-transact-sql) after first execution.</span></span>  
  
## <a name="maintenance-of-in-memory-oltp-dlls"></a><span data-ttu-id="5e3b7-119">Wartung von In-Memory OLTP-DLLs</span><span class="sxs-lookup"><span data-stu-id="5e3b7-119">Maintenance of In-Memory OLTP DLLs</span></span>  
 <span data-ttu-id="5e3b7-120">Die folgende Abfrage zeigt alle DLLs für Tabellen und gespeicherte Prozeduren, die aktuell in den Arbeitsspeicher des Servers geladen sind:</span><span class="sxs-lookup"><span data-stu-id="5e3b7-120">The following query shows all table and stored procedure DLLs currently loaded in memory on the server:</span></span>  
  
```sql  
SELECT name, description FROM sys.dm_os_loaded_modules  
where description = 'XTP Native DLL'  
```  
  
 <span data-ttu-id="5e3b7-121">Datenbankadministratoren müssen die Dateien, die von der systeminterne Kompilierung erstellt werden, nicht manuell pflegen.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-121">Database administrators do not need to maintain files that are generated by a native compilation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5e3b7-122">entfernt automatisch generierte Dateien, die nicht mehr benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-122">automatically removes generated files that are no longer needed.</span></span> <span data-ttu-id="5e3b7-123">Beispielsweise werden generierte Dateien gelöscht, wenn eine Tabelle und eine gespeicherte Prozedur gelöscht werden, oder wenn eine Datenbank gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-123">For example, generated files will be deleted when a table and stored procedure is deleted, or if a database is dropped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e3b7-124">Wenn Kompilierung fehlschlägt oder unterbrochen wird, werden einige generierte Dateien nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-124">If compilation fails or is interrupted, some generated files are not removed.</span></span> <span data-ttu-id="5e3b7-125">Diese Dateien werden absichtlich beibehalten, um die Unterstützbarkeit zu gewährleisten. Sie werden beim Löschen der Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-125">These files are intentionally left behind for supportability and are removed when the database is dropped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e3b7-126">Beim Datenbankstart kompiliert SQL Server die DLLs für alle Tabellen, die für die Datenbankwiederherstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-126">During database startup, SQL Server compiles DLLs for all tables needed for database recovery.</span></span> <span data-ttu-id="5e3b7-127">Wenn eine Tabelle unmittelbar vor einem Neustart der Datenbank gelöscht wurde, können immer noch Reste der Tabelle in den Prüfpunktdateien oder dem Transaktionsprotokoll vorhanden sein, sodass die DLL für die Tabelle beim Datenbankstart neu kompiliert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-127">If a table was dropped just prior to a database restart there can still be remnants of the table in the checkpoint files or the transaction log so the DLL for the table might be recompiled during database startup.</span></span> <span data-ttu-id="5e3b7-128">Nach dem Neustart wird die DLL entladen, und die Dateien durch den normalen Bereigungsprozess entfernt.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-128">After restart the DLL will be unloaded and the files will be removed by the normal cleanup process.</span></span>  
  
## <a name="native-compilation-of-tables"></a><span data-ttu-id="5e3b7-129">Systeminterne Kompilierung von Tabellen</span><span class="sxs-lookup"><span data-stu-id="5e3b7-129">Native Compilation of Tables</span></span>  
 <span data-ttu-id="5e3b7-130">Beim Erstellen einer speicheroptimierten Tabelle mithilfe der `CREATE TABLE`-Anweisung werden die Tabelleninformationen in die Datenbankmetadaten geschrieben und die Tabellen- und Indexstrukturen im Arbeitsspeicher erstellt.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-130">Creating a memory-optimized table using the `CREATE TABLE` statement results in the table information being written to the database metadata and the table and index structures created in memory.</span></span> <span data-ttu-id="5e3b7-131">Die Tabelle wird außerdem zu einer DLL kompiliert.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-131">The table will also be compiled to a DLL.</span></span>  
  
 <span data-ttu-id="5e3b7-132">Betrachten Sie das folgende Beispielskript, in dem eine Datenbank und eine speicheroptimierte Tabelle erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="5e3b7-132">Consider the following sample script, which creates a database and a memory-optimized table:</span></span>  
  
```sql  
use master  
go  
create database db1  
go  
alter database db1 add filegroup db1_mod contains memory_optimized_data  
go  
-- adapt filename as needed  
alter database db1 add file (name='db1_mod', filename='c:\data\db1_mod') to filegroup db1_mod  
go  
use db1  
go  
create table dbo.t1  
   (c1 int not null primary key nonclustered,  
    c2 INT)  
with (memory_optimized=on)  
go  
-- retrieve the path of the DLL for table t1  
select name, description FROM sys.dm_os_loaded_modules  
where name like '%xtp_t_' + cast(db_id() as varchar(10)) + '_' + cast(object_id('dbo.t1') as varchar(10)) + '.dll'  
go  
```  
  
 <span data-ttu-id="5e3b7-133">Durch das Erstellen der Tabelle wird auch die Tabellen-DLL erstellt und in den Arbeitsspeicher geladen.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-133">Creating the table also creates the table DLL and loads the DLL in memory.</span></span> <span data-ttu-id="5e3b7-134">Die DMV-Abfrage unmittelbar nach der CREATE TABLE-Anweisung ruft den Pfad der Tabellen-DLL ab.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-134">The DMV query immediately after the CREATE TABLE statement retrieves the path of the table DLL.</span></span>  
  
 <span data-ttu-id="5e3b7-135">Die Tabellen-DLL kann die Indexstrukturen und das Zeilenformat der Tabelle lesen.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-135">The table DLL understands the index structures and row format of the table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5e3b7-136">verwendet die DLL für das Durchsuchen von Indizes, das Abrufen von Zeilen und das Speichern von Zeileninhalten.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-136">uses the DLL for traversing indexes, retrieving rows, as well as storing the contents of the rows.</span></span>  
  
## <a name="native-compilation-of-stored-procedures"></a><span data-ttu-id="5e3b7-137">Systeminterne Kompilierung gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="5e3b7-137">Native Compilation of Stored Procedures</span></span>  
 <span data-ttu-id="5e3b7-138">Gespeicherte Prozeduren, die mit NATIVE_COMPILATION markiert sind, werden systemintern kompiliert.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-138">Stored procedures that are marked with NATIVE_COMPILATION are natively compiled.</span></span> <span data-ttu-id="5e3b7-139">Dies bedeutet, dass alle [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen in der Prozedur in systemeigenen Code kompiliert werden, um eine effiziente Ausführung der leistungskritischen Geschäftslogik zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-139">This means the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the procedure are all compiled to native code for efficient execution of performance-critical business logic.</span></span>  
  
 <span data-ttu-id="5e3b7-140">Weitere Informationen zu systemintern kompilierten gespeicherten Prozeduren finden Sie unter [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5e3b7-140">For more information about natively compiled stored procedures, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="5e3b7-141">Betrachten Sie das folgende Beispiel für eine gespeicherte Prozedur, die Zeilen in die Tabelle t1 aus dem vorherigen Beispiel einfügt:</span><span class="sxs-lookup"><span data-stu-id="5e3b7-141">Consider the following sample stored procedure, which inserts rows in the table t1 from the previous example:</span></span>  
  
```sql  
create procedure dbo.native_sp  
with native_compilation, schemabinding, execute as owner  
as  
begin atomic  
with (transaction isolation level=snapshot, language=N'us_english')  
  
  declare @i int = 1000000  
  while @i > 0  
  begin  
    insert dbo.t1 values (@i, @i+1)  
    set @i -= 1  
  end  
  
end  
go  
exec dbo.native_sp  
go  
-- reset  
delete from dbo.t1  
go  
```  
  
 <span data-ttu-id="5e3b7-142">Die DLL für native_sp kann direkt mit der DLL für t1 sowie mit der Speicher-Engine von In-Memory-OLTP interagieren, sodass Zeilen in der kürzestmöglichen Zeit eingefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-142">The DLL for native_sp can interact directly with the DLL for t1, as well as the In-Memory OLTP storage engine, to insert the rows as fast as possible.</span></span>  
  
 <span data-ttu-id="5e3b7-143">Der Compiler von In-Memory OLTP nutzt den Abfrageoptimierer, um einen effizienten Ausführungsplan für die einzelnen Abfragen in der gespeicherten Prozedur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-143">The In-Memory OLTP compiler leverages the query optimizer to create an efficient execution plan for each of the queries in the stored procedure.</span></span> <span data-ttu-id="5e3b7-144">Beachten Sie, dass systemintern kompilierte gespeicherte Prozeduren nicht automatisch neu kompiliert werden, wenn sich die Daten in der Tabelle ändern.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-144">Note that natively compiled stored procedures are not automatically recompiled if the data in the table changes.</span></span> <span data-ttu-id="5e3b7-145">Weitere Informationen zur Verwaltung von Statistiken und gespeicherten Prozeduren mit In-Memory-OLTP finden Sie unter [Statistiken für speicheroptimierte Tabellen](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="5e3b7-145">For more information on maintaining statistics and stored procedures with In-Memory OLTP see [Statistics for Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
## <a name="security-considerations-for-native-compilation"></a><span data-ttu-id="5e3b7-146">Sicherheitsüberlegungen für systeminterne Kompilierung</span><span class="sxs-lookup"><span data-stu-id="5e3b7-146">Security Considerations for Native Compilation</span></span>  
 <span data-ttu-id="5e3b7-147">Die systeminterne Kompilierung von Tabellen und gespeicherten Prozeduren verwendet den In-Memory OLTP-Compiler.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-147">Native compilation of tables and stored procedures uses the In-Memory OLTP compiler.</span></span> <span data-ttu-id="5e3b7-148">Dieser Compiler erzeugt Dateien, die auf den Datenträger geschrieben und in den Arbeitsspeicher geladen werden.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-148">This compiler produces files that are written to disk and loaded into memory.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5e3b7-149">verwendet die folgenden Mechanismen, um den Zugriff auf diese Dateien einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-149">uses the following mechanisms to limit access to these files.</span></span>  
  
### <a name="native-compiler"></a><span data-ttu-id="5e3b7-150">Systemeigener Compiler</span><span class="sxs-lookup"><span data-stu-id="5e3b7-150">Native Compiler</span></span>  
 <span data-ttu-id="5e3b7-151">Die ausführbare Compilerdatei sowie die Binärdateien und Headerdateien, die für die systeminterne Kompilierung erforderlich sind, werden als Teil der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz unter dem Ordner MSSQL\Binn\Xtp installiert.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-151">The compiler executable, as well as binaries and header files required for native compilation are installed as part of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance under the folder MSSQL\Binn\Xtp.</span></span> <span data-ttu-id="5e3b7-152">Wenn die Standard Instanz unter "c:\Programme" installiert wird, werden die Compilerdateien in "c:\Programme \\ [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \mssql12." installiert. Mssqlserver\mssql\binn\xtp.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-152">So, if the default instance is installed under C:\Program Files, the compiler files are installed in C:\Program Files\\[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\MSSQL12.MSSQLSERVER\MSSQL\Binn\Xtp.</span></span>  
  
 <span data-ttu-id="5e3b7-153">Um den Zugriff auf den Compiler einzuschränken, verwendet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Zugriffssteuerungslisten (ACLs), um den Zugriff auf die Binärdateien einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-153">To limit access to the compiler, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses access control lists (ACLs) to restrict access to binary files.</span></span> <span data-ttu-id="5e3b7-154">Alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Binärdateien sind vor Änderungen oder Manipulation durch ACLs geschützt.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-154">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] binaries are protected against modification or tampering through ACLs.</span></span> <span data-ttu-id="5e3b7-155">Die ACLs des systemeigenen Compilers schränken auch das Verwenden des Compilers ein; nur das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienstkonto und Systemadministratoren haben Lese- und Ausführungsberechtigungen für systemeigene Compilerdateien.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-155">The native compiler's ACLs also limit use of the compiler; only the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and system administrators have read and execute permissions for native compiler files.</span></span>  
  
### <a name="files-generated-by-a-native-compilation"></a><span data-ttu-id="5e3b7-156">Durch eine systeminterne Kompilierung generierte Dateien</span><span class="sxs-lookup"><span data-stu-id="5e3b7-156">Files Generated by a Native Compilation</span></span>  
 <span data-ttu-id="5e3b7-157">Die Dateien, die erzeugt werden, wenn eine Tabelle oder eine gespeicherte Prozedur kompiliert wird, umfassen die DLL und Zwischendateien, einschließlich Dateien mit den folgenden Erweiterungen: .c, .obj, .xml und .pdb.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-157">The files produced when a table or stored procedure is compiled include the DLL and intermediate files including files with the following extensions: .c, .obj, .xml, and .pdb.</span></span> <span data-ttu-id="5e3b7-158">Die generierten Dateien werden in einem Unterordner des standardmäßigen Datenordners gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-158">The generated files are saved in a subfolder of the default data folder.</span></span> <span data-ttu-id="5e3b7-159">Der Unterordner wird Xtp genannt.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-159">The subfolder is called Xtp.</span></span> <span data-ttu-id="5e3b7-160">Wenn Sie die Standard Instanz mit dem standardmäßigen Datenordner installieren, werden die generierten Dateien in "c:\Programme \\ [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \mssql12." platziert. Mssqlserver\mssql\data\xtp.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-160">When installing the default instance with the default data folder, the generated files are placed in C:\Program Files\\[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\MSSQL12.MSSQLSERVER\MSSQL\DATA\Xtp.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5e3b7-161">verhindert eine Manipulation der generierten DLLs auf drei Arten:</span><span class="sxs-lookup"><span data-stu-id="5e3b7-161">prevents tampering with the generated DLLs in three ways:</span></span>  
  
-   <span data-ttu-id="5e3b7-162">Wenn eine Tabelle oder eine gespeicherte Prozedur zu einer DLL kompiliert wird, wird diese DLL sofort in den Arbeitsspeicher geladen und mit dem sqlserver.exe-Prozess verknüpft.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-162">When a table or stored procedure is compiled to a DLL, this DLL is immediately loaded into memory and linked to the sqlserver.exe process.</span></span> <span data-ttu-id="5e3b7-163">Eine DLL kann nicht geändert werden, während sie mit einem Prozess verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-163">A DLL cannot be modified while it is linked to a process.</span></span>  
  
-   <span data-ttu-id="5e3b7-164">Wenn eine Datenbank neu gestartet wird, werden alle Tabellen und gespeicherten Prozeduren auf der Grundlage der Datenbankmetadaten neu kompiliert (entfernt und neu erstellt).</span><span class="sxs-lookup"><span data-stu-id="5e3b7-164">When a database is restarted, all tables and stored procedures are recompiled (removed and recreated) based on the database metadata.</span></span> <span data-ttu-id="5e3b7-165">Hierdurch werden alle Änderungen, die von einem böswilligen Benutzer an einer generierten Datei vorgenommen wurden, entfernt.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-165">This will remove any changes made to a generated file by a malicious agent.</span></span>  
  
-   <span data-ttu-id="5e3b7-166">Die generierten Dateien werden als Teil der Benutzerdaten betrachtet und verfügen über die gleichen Sicherheitseinschränkungen (über ACLs) wie Datenbankdateien: Nur das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienstkonto und Systemadministratoren können auf diese Dateien zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-166">The generated files are considered part of user data, and have the same security restrictions, via ACLs, as database files: only the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and system administrators can access these files.</span></span>  
  
 <span data-ttu-id="5e3b7-167">Zum Verwalten dieser Dateien ist keine Benutzerinteraktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-167">No user interaction is needed to manage these files.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5e3b7-168">erstellt und entfernt die Dateien nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="5e3b7-168">will create and remove the files as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e3b7-169">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5e3b7-169">See Also</span></span>  
 <span data-ttu-id="5e3b7-170">[Speicher optimierte Tabellen](memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="5e3b7-170">[Memory-Optimized Tables](memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="5e3b7-171">Nativ kompilierte gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="5e3b7-171">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
