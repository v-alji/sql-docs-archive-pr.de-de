---
title: Sortierungen und Codepages | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c626dcac-0474-432d-acc0-cfa643345372
author: stevestein
ms.author: sstein
ms.openlocfilehash: ab904771fa8ac4acf25a624cbf3e1139f7e96434
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619362"
---
# <a name="collations-and-code-pages"></a><span data-ttu-id="89396-102">Sortierungen und Codepages</span><span class="sxs-lookup"><span data-stu-id="89396-102">Collations and Code Pages</span></span>
  [!INCLUDE[hek_2](../includes/hek-2-md.md)] <span data-ttu-id="89396-103">weist Einschränkungen bei unterstützten Codepages für (var)char-Spalten in speicheroptimierten Tabellen und unterstützten Sortierungen auf, die in Indizes und in systemintern kompilierten gespeicherten Prozeduren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89396-103">has restrictions on supported code pages for (var)char columns in memory-optimized tables and supported collations used in indexes and natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="89396-104">Die Codepage für einen (var)char-Wert bestimmt die Zuordnung zwischen Zeichen und der Bytedarstellung, die in der Tabelle gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="89396-104">The code page for a (var)char value determines the mapping between characters and the byte representation that is stored in the table.</span></span> <span data-ttu-id="89396-105">So entspricht z. B. bei der Windows Latin 1-Codepage (1252; der[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Standard) das Zeichen „a“ dem Byte 0x61.</span><span class="sxs-lookup"><span data-stu-id="89396-105">For example, with the Windows Latin 1 code page (1252; the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] default), the character 'a' corresponds to the byte 0x61.</span></span>  
  
 <span data-ttu-id="89396-106">Die Codepage eines (var)char-Werts wird durch die Sortierung bestimmt, die dem Wert zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="89396-106">The code page of a (var)char value is determined by the collation associated with the value.</span></span> <span data-ttu-id="89396-107">So hat die Sortierung SQL_Latin1_General_CP1_CI_AS beispielsweise die zugeordnete Codepage 1252.</span><span class="sxs-lookup"><span data-stu-id="89396-107">For example, the collation SQL_Latin1_General_CP1_CI_AS has the associated code page 1252.</span></span>  
  
 <span data-ttu-id="89396-108">Die Sortierung eines Werts wird entweder von der Datenbanksortierung geerbt oder kann mithilfe des COLLATE-Schlüsselworts explizit angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="89396-108">The collation of a value is either inherited from the database collation, or can be specified explicitly using the COLLATE keyword.</span></span> <span data-ttu-id="89396-109">Die Datenbanksortierung kann nicht geändert werden, wenn die Datenbank speicheroptimierte Tabellen oder systemintern kompilierte gespeicherte Prozeduren enthält.</span><span class="sxs-lookup"><span data-stu-id="89396-109">Database collation cannot be changed if the database contains memory-optimized tables or natively compiled stored procedures.</span></span> <span data-ttu-id="89396-110">Im folgenden Beispiel wird die Datenbanksortierung festgelegt und eine Tabelle erstellt, die eine Spalte mit einer anderen Sortierung hat.</span><span class="sxs-lookup"><span data-stu-id="89396-110">The following example sets the database collation and creates a table, which has a column with a different collation.</span></span> <span data-ttu-id="89396-111">Die Datenbank verwendet die Latin-Sortierung, bei der die Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="89396-111">The database uses Latin case-insensitive collation.</span></span>  
  
 <span data-ttu-id="89396-112">Indizes können nur für Zeichenfolgenspalten erstellt werden, wenn sie eine BIN2-Sortierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="89396-112">Indexes can only be created on string columns if they use a BIN2 collation.</span></span> <span data-ttu-id="89396-113">Die LastName-Variable verwendet BIN2-Sortierung.</span><span class="sxs-lookup"><span data-stu-id="89396-113">The LastName variable uses BIN2 collation.</span></span> <span data-ttu-id="89396-114">FirstName verwendet den Datenbankstandardwert, der CI_AS (Unterscheidung nach Groß-/Kleinschreibung, Unterscheidung nach Akzent) ist.</span><span class="sxs-lookup"><span data-stu-id="89396-114">FirstName uses the database default, which is CI_AS (case-insensitive, accent-sensitive).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="89396-115">ORDER BY oder GROUP BY kann nicht für Spalten mit Indexzeichenfolgen verwendet werden, die keine BIN2-Sortierung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="89396-115">You cannot use order by or group by on index string columns that do not use BIN2 collation.</span></span>  
  
```sql  
CREATE DATABASE IMOLTP  
  
ALTER DATABASE IMOLTP ADD FILEGROUP IMOLTP_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE IMOLTP ADD FILE( NAME = 'IMOLTP_mod' , FILENAME = 'c:\data\IMOLTP_mod') TO FILEGROUP IMOLTP_mod;  
--GO  
  
--  set the database collations  
ALTER DATABASE IMOLTP COLLATE Latin1_General_100_CI_AS  
GO  
  
--  
USE IMOLTP   
GO  
  
-- create a table with collation  
CREATE TABLE Employees (  
  EmployeeID int NOT NULL ,   
  LastName nvarchar(20) COLLATE Latin1_General_100_BIN2 NOT NULL INDEX IX_LastName NONCLUSTERED,   
  FirstName nvarchar(10) NOT NULL ,  
  CONSTRAINT PK_Employees PRIMARY KEY NONCLUSTERED HASH(EmployeeID)  WITH (BUCKET_COUNT=1024)  
) WITH (MEMORY_OPTIMIZED=ON, DURABILITY=SCHEMA_AND_DATA)  
GO  
```  
  
 <span data-ttu-id="89396-116">Die folgenden Einschränkungen gelten für speicheroptimierte Tabellen und systemintern kompilierte gespeicherte Prozeduren:</span><span class="sxs-lookup"><span data-stu-id="89396-116">The following restrictions apply to memory-optimized tables and natively compiled stored procedures:</span></span>  
  
-   <span data-ttu-id="89396-117">(var)char-Spalten in speicheroptimierten Tabellen müssen die Sortierung der Codepage 1252 verwenden.</span><span class="sxs-lookup"><span data-stu-id="89396-117">(var)char columns in memory-optimized tables must use code page 1252 collation.</span></span> <span data-ttu-id="89396-118">Diese Einschränkung gilt nicht für n(var)char-Spalten.</span><span class="sxs-lookup"><span data-stu-id="89396-118">This restriction does not apply to n(var)char columns.</span></span> <span data-ttu-id="89396-119">Der folgende Code ruft alle 1252-Sortierungen ab:</span><span class="sxs-lookup"><span data-stu-id="89396-119">The following code retrieves all 1252 collations:</span></span>  
  
    ```sql  
    -- all supported collations for (var)char columns in memory-optimized tables  
    select * from sys.fn_helpcollations()  
    where collationproperty(name, 'codepage') = 1252;  
    ```  
  
     <span data-ttu-id="89396-120">Wenn Sie nicht-lateinischen Zeichen speichern müssen, verwenden Sie n(var)char-Spalten.</span><span class="sxs-lookup"><span data-stu-id="89396-120">If you need to store non-Latin characters, use n(var)char columns.</span></span>  
  
-   <span data-ttu-id="89396-121">Indizes für (n)(var)char-Spalten können nur mit BIN2-Sortierungen angegeben werden (siehe erstes Beispiel).</span><span class="sxs-lookup"><span data-stu-id="89396-121">Indexes on (n)(var)char columns can only be specified with BIN2 collations (see the first example).</span></span> <span data-ttu-id="89396-122">Die folgende Abfrage ruft alle unterstützten BIN2-Sortierungen ab:</span><span class="sxs-lookup"><span data-stu-id="89396-122">The following query retrieves all supported BIN2 collations:</span></span>  
  
    ```sql  
    -- all supported collations for indexes on memory-optimized tables and   
    -- comparison/sorting in natively compiled stored procedures  
    select * from sys.fn_helpcollations() where name like '%BIN2'  
    ```  
  
     <span data-ttu-id="89396-123">Wenn Sie über interpretiertes [!INCLUDE[tsql](../includes/tsql-md.md)] auf die Tabelle zugreifen, können Sie das `COLLATE`-Schlüsselwort verwenden, um die Sortierung mit Ausdrücken oder Sortiervorgängen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="89396-123">If you access the table through interpreted [!INCLUDE[tsql](../includes/tsql-md.md)], you can use the `COLLATE` keyword to change the collation with expressions or sort operations.</span></span> <span data-ttu-id="89396-124">Siehe das letzte Beispiel.</span><span class="sxs-lookup"><span data-stu-id="89396-124">See the last example for a sample of this.</span></span>  
  
-   <span data-ttu-id="89396-125">Systemintern kompilierte gespeicherte Prozeduren können Parameter, lokale Variablen oder Zeichenfolgenkonstanten vom Typ (var)char nicht verwenden, wenn die Datenbanksortierung keine Sortierung der Codepage 1252 ist.</span><span class="sxs-lookup"><span data-stu-id="89396-125">Natively compiled stored procedures cannot use parameters, local variables, or string constants of (var)char type if the database collation is not a code page 1252 collation.</span></span>  
  
-   <span data-ttu-id="89396-126">Alle Ausdrücke und Sortiervorgänge in systemintern kompilierten gespeicherten Prozeduren müssen BIN2-Sortierungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="89396-126">All expressions and sort operations inside natively compiled stored procedures must use BIN2 collations.</span></span> <span data-ttu-id="89396-127">Es wird impliziert, dass alle Vergleiche und Sortiervorgänge auf den Unicode-Codepunkten der Zeichen (binäre Darstellung) basieren.</span><span class="sxs-lookup"><span data-stu-id="89396-127">The implication is that all comparisons and sort operations are based on the Unicode code points of the characters (binary representations).</span></span> <span data-ttu-id="89396-128">Beispielsweise wird bei allen Sortierungen nach Groß-/Kleinschreibung unterschieden ("Z" kommt vor "a").</span><span class="sxs-lookup"><span data-stu-id="89396-128">For example all sorting is case sensitive ('Z' comes before 'a').</span></span> <span data-ttu-id="89396-129">Bei Bedarf kann für Sortierungen und Vergleiche ohne Beachtung der Groß-/Kleinschreibung interpretiertes [!INCLUDE[tsql](../includes/tsql-md.md)] verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89396-129">If necessary, use interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] for case-insensitive sorting and comparison.</span></span>  
  
-   <span data-ttu-id="89396-130">Abschneiden von UTF-16-Daten wird in systemintern kompilierten gespeicherten Prozeduren nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="89396-130">Truncation of UTF-16 data is not supported inside natively compiled stored procedures.</span></span> <span data-ttu-id="89396-131">Dies bedeutet, dass n (var) char (*n*)-Werte nicht in den Typ n (var) char (*i*) konvertiert werden können *, wenn*  <  *n*die Sortierung über _SC Eigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="89396-131">This means that n(var)char(*n*) values cannot be converted to type n(var)char(*i*), if *i* < *n*, if the collation has _SC property.</span></span> <span data-ttu-id="89396-132">Beispielsweise wird Folgendes nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="89396-132">For example, the following is not supported:</span></span>  
  
    ```sql  
    -- column definition using an _SC collation  
     c2 nvarchar(200) collate Latin1_General_100_CS_AS_SC not null   
    -- assignment to a smaller variable, requiring truncation  
     declare @c2 nvarchar(100) = '';  
     select @c2 = c2  
    ```  
  
     <span data-ttu-id="89396-133">Funktionen zur Zeichenfolgenmanipulation wie LEN, SUBSTRING, LTRIM und RTRIM mit UTF-16-Daten werden in systemintern kompilierten gespeicherten Prozeduren nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="89396-133">String manipulation functions, such as LEN, SUBSTRING, LTRIM, and RTRIM with UTF-16 data are not supported inside natively compiled stored procedures.</span></span> <span data-ttu-id="89396-134">Sie können diese Funktionen zur Zeichenfolgenmanipulation für n(var)char-Werte mit _SC-Sortierung nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="89396-134">You cannot use these string manipulation functions for n(var)char values that have an _SC collation.</span></span>  
  
     <span data-ttu-id="89396-135">Deklarieren Sie Variablen mit Typen, die ausreichend groß sind, sodass ein Abschneiden vermieden wird.</span><span class="sxs-lookup"><span data-stu-id="89396-135">Declare variables using types that are large enough to avoid truncation.</span></span>  
  
 <span data-ttu-id="89396-136">Im folgenden Beispiel werden einige der Auswirkungen und Problemumgehungen zu Sortierungseinschränkungen in In-Memory OLTP gezeigt.</span><span class="sxs-lookup"><span data-stu-id="89396-136">The following example shows some of the implications and workarounds for the collation limitations in In-Memory OLTP.</span></span> <span data-ttu-id="89396-137">Im Beispiel wird die oben angegebene Mitarbeitertabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="89396-137">The example uses the Employees table specified above.</span></span> <span data-ttu-id="89396-138">In diesem Beispiel werden alle Mitarbeiter aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="89396-138">This sample list all employees .</span></span> <span data-ttu-id="89396-139">Beachten Sie, dass aufgrund der binären Sortierung bei LastName die groß geschriebenen Namen vor die klein geschriebenen sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="89396-139">Notice that for LastName, due to the binary collation, the upper case names are sorted before lower case.</span></span> <span data-ttu-id="89396-140">Daher kommt "Thomas" vor "nolan", da Großbuchstaben niedrigere Codepunkte haben.</span><span class="sxs-lookup"><span data-stu-id="89396-140">Therefore, 'Thomas' comes before 'nolan' because upper case characters have lower code points.</span></span> <span data-ttu-id="89396-141">FirstName hat eine Sortierung, bei der die Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="89396-141">FirstName has a case-insensitive collation.</span></span> <span data-ttu-id="89396-142">Daher erfolgt die Sortierung nach Buchstabe des Alphabets, nicht nach Codepunkt der Zeichen.</span><span class="sxs-lookup"><span data-stu-id="89396-142">So, sorting is by letter of the alphabet, not code point of the characters.</span></span>  
  
```sql  
-- insert a number of values  
INSERT Employees VALUES (1,'thomas', 'john')  
INSERT Employees VALUES (2,'Thomas', 'rupert')  
INSERT Employees VALUES (3,'Thomas', 'Jack')  
INSERT Employees VALUES (4,'Thomas', 'annie')  
INSERT Employees VALUES (5,'nolan', 'John')  
GO  
  
-- ===========  
SELECT EmployeeID, LastName, FirstName FROM Employees  
ORDER BY LastName, FirstName  
GO  
  
-- ===========  
-- specify collation: sorting uses case-insensitive collation, thus 'nolan' comes before 'Thomas'  
SELECT * FROM Employees  
ORDER BY LastName COLLATE Latin1_General_100_CI_AS, FirstName  
GO  
  
-- ===========  
-- retrieve employee by Name  
-- must use BIN2 collation for comparison in natively compiled stored procedures  
CREATE PROCEDURE usp_EmployeeByName @LastName nvarchar(20), @FirstName nvarchar(10)  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH   
(  TRANSACTION ISOLATION LEVEL = SNAPSHOT,  
  LANGUAGE = N'us_english'  
)  
  SELECT EmployeeID, LastName, FirstName FROM dbo.Employees  
  WHERE   
    LastName = @LastName AND  
    FirstName COLLATE Latin1_General_100_BIN2 = @FirstName  
  
END  
GO  
  
-- this does not return any rows, as EmployeeID 1 has first name 'john', which is not equal to 'John' in a binary collation  
EXEC usp_EmployeeByName 'thomas', 'John'  
  
-- this retrieves EmployeeID 1  
EXEC usp_EmployeeByName 'thomas', 'john'  
```  
  
## <a name="see-also"></a><span data-ttu-id="89396-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89396-143">See Also</span></span>  
 [<span data-ttu-id="89396-144">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="89396-144">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
