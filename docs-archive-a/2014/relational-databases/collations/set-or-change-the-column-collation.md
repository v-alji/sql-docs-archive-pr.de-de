---
title: Festlegen oder Ändern der Spaltensortierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tempdb database [SQL Server], collations
- collations [SQL Server], column
ms.assetid: d7a9638b-717c-4680-9b98-8849081e08be
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05b8211569b6ce83faaec043e5eb527a60f0ddab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622698"
---
# <a name="set-or-change-the-column-collation"></a><span data-ttu-id="ab31f-102">Festlegen oder Ändern der Spaltensortierung</span><span class="sxs-lookup"><span data-stu-id="ab31f-102">Set or Change the Column Collation</span></span>
  <span data-ttu-id="ab31f-103">Sie können die Datenbanksortierung für `char`-, `varchar`-, `text`-, `nchar`-, `nvarchar`- und `ntext`-Daten überschreiben, indem Sie eine andere Sortierung für eine bestimmte Spalte einer Tabelle angeben und dann eine der folgenden Optionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="ab31f-103">You can override the database collation for `char`, `varchar`, `text`, `nchar`, `nvarchar`, and `ntext` data by specifying a different collation for a specific column of a table and using one of the following:</span></span>  
  
-   <span data-ttu-id="ab31f-104">Die COLLATE-Klausel von [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) und [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ab31f-104">The COLLATE clause of [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) and [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span> <span data-ttu-id="ab31f-105">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ab31f-105">For example:</span></span>  
  
    ```  
    CREATE TABLE dbo.MyTable  
      (PrimaryKey   int PRIMARY KEY,  
       CharCol      varchar(10) COLLATE French_CI_AS NOT NULL  
      );  
    GO  
    ALTER TABLE dbo.MyTable ALTER COLUMN CharCol  
                varchar(10)COLLATE Latin1_General_CI_AS NOT NULL;  
    GO  
    ```  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="ab31f-106">.</span><span class="sxs-lookup"><span data-stu-id="ab31f-106">.</span></span> <span data-ttu-id="ab31f-107">Weitere Informationen finden Sie unter [Collation and Unicode Support](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="ab31f-107">For more information, [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
-   <span data-ttu-id="ab31f-108">Mithilfe der- `Column.Collation` Eigenschaft in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO).</span><span class="sxs-lookup"><span data-stu-id="ab31f-108">Using the `Column.Collation` property in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="ab31f-109">Sie können die Sortierung einer Spalte nicht ändern, wenn folgende Objekte aktuell auf die Spalte verweisen:</span><span class="sxs-lookup"><span data-stu-id="ab31f-109">You cannot change the collation of a column that is currently referenced by any one of the following:</span></span>  
  
-   <span data-ttu-id="ab31f-110">Eine berechnete Spalte.</span><span class="sxs-lookup"><span data-stu-id="ab31f-110">A computed column</span></span>  
  
-   <span data-ttu-id="ab31f-111">Ein Index.</span><span class="sxs-lookup"><span data-stu-id="ab31f-111">An index</span></span>  
  
-   <span data-ttu-id="ab31f-112">Verteilungsstatistiken, die entweder automatisch oder mithilfe der CREATE STATISTICS-Anweisung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ab31f-112">Distribution statistics, either generated automatically or by the CREATE STATISTICS statement</span></span>  
  
-   <span data-ttu-id="ab31f-113">Eine CHECK-Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="ab31f-113">A CHECK constraint</span></span>  
  
-   <span data-ttu-id="ab31f-114">Eine FOREIGN KEY-Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="ab31f-114">A FOREIGN KEY constraint</span></span>  
  
 <span data-ttu-id="ab31f-115">Wenn Sie **tempdb**verwenden, enthält die [COLLATE](/sql/t-sql/statements/collations) -Klausel eine *database_defauls* -Option, mit der angegeben werden kann, dass für eine Spalte einer temporären Tabelle anstelle der Sortierung von **tempdb**die Standardsortierung der aktuellen Benutzerdatenbank für die Verbindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ab31f-115">When you work with **tempdb**, the [COLLATE](/sql/t-sql/statements/collations) clause includes a *database_default* option to specify that a column in a temporary table uses the collation default of the current user database for the connection instead of the collation of **tempdb**.</span></span>  
  
## <a name="collations-and-text-columns"></a><span data-ttu-id="ab31f-116">Sortierungen und text-Spalten</span><span class="sxs-lookup"><span data-stu-id="ab31f-116">Collations and text Columns</span></span>  
 <span data-ttu-id="ab31f-117">Sie können Werte in einer `text`-Spalte einfügen und aktualisieren, deren Sortierung sich von der Codepage der Standardsortierung der Datenbank unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="ab31f-117">You can insert or update values in a `text` column whose collation is different from the code page of the default collation of the database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ab31f-118">werden die Werte implizit in die Sortierung der Spalte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ab31f-118">implicitly converts the values to the collation of the column.</span></span>  
  
## <a name="collations-and-tempdb"></a><span data-ttu-id="ab31f-119">Sortierungen und tempdb</span><span class="sxs-lookup"><span data-stu-id="ab31f-119">Collations and tempdb</span></span>  
 <span data-ttu-id="ab31f-120">Die **tempdb** -Datenbank wird bei jedem Start von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erstellt und weist die gleiche Standardsortierung wie die **model** -Datenbank auf.</span><span class="sxs-lookup"><span data-stu-id="ab31f-120">The **tempdb** database is built every time [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started and has the same default collation as the **model** database.</span></span> <span data-ttu-id="ab31f-121">Dabei handelt es sich normalerweise um die gleiche Sortierung wie die Standardsortierung der Instanz.</span><span class="sxs-lookup"><span data-stu-id="ab31f-121">This is typically the same as the default collation of the instance.</span></span> <span data-ttu-id="ab31f-122">Wenn Sie eine Benutzerdatenbank erstellen und eine andere Standardsortierung als für die **model**-Datenbank angeben, verwendet die Benutzerdatenbank eine andere Standardsortierung als die **tempdb**-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ab31f-122">If you create a user database and specify a different default collation than **model**, the user database has a different default collation than **tempdb**.</span></span> <span data-ttu-id="ab31f-123">Alle temporären gespeicherten Prozeduren oder temporären Tabellen werden in **tempdb**erstellt und gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ab31f-123">All temporary stored procedures or temporary tables are created and stored in **tempdb**.</span></span> <span data-ttu-id="ab31f-124">Dies bedeutet, dass alle impliziten Spalten in temporären Tabellen und alle Konstanten, Variablen und Parameter mit erzwingbaren Standards in temporär gespeicherten Prozeduren andere Sortierungen aufweisen als die vergleichbaren Objekte, die in dauerhaften Tabellen und gespeicherten Prozeduren erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ab31f-124">This means that all implicit columns in temporary tables and all coercible-default constants, variables, and parameters in temporary stored procedures have collations that are different from comparable objects created in permanent tables and stored procedures.</span></span>  
  
 <span data-ttu-id="ab31f-125">Dies kann zu Problemen hinsichtlich einer Nichtübereinstimmung in Sortierungen zwischen benutzerdefinierten Datenbanken und Systemdatenbankobjekten führen.</span><span class="sxs-lookup"><span data-stu-id="ab31f-125">This could lead to problems with a mismatch in collations between user-defined databases and system database objects.</span></span> <span data-ttu-id="ab31f-126">Eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet z. B. die Latin1_General_CS_AS-Sortierung, und Sie führen die folgenden Anweisungen aus:</span><span class="sxs-lookup"><span data-stu-id="ab31f-126">For example, an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the Latin1_General_CS_AS collation and you execute the following statements:</span></span>  
  
```  
CREATE DATABASE TestDB COLLATE Estonian_CS_AS;  
USE TestDB;  
CREATE TABLE TestPermTab (PrimaryKey int PRIMARY KEY, Col1 nchar );  
```  
  
 <span data-ttu-id="ab31f-127">In diesem System verwendet die **tempdb** -Datenbank die Latin1_General_CS_AS-Sortierung mit Codepage 1252, und `TestDB` und `TestPermTab.Col1` verwenden die `Estonian_CS_AS` -Sortierung mit Codepage 1257.</span><span class="sxs-lookup"><span data-stu-id="ab31f-127">In this system, the **tempdb** database uses the Latin1_General_CS_AS collation with code page 1252, and `TestDB` and `TestPermTab.Col1` use the `Estonian_CS_AS` collation with code page 1257.</span></span> <span data-ttu-id="ab31f-128">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ab31f-128">For example:</span></span>  
  
```  
USE TestDB;  
GO  
-- Create a temporary table with the same column declarations  
-- as TestPermTab  
CREATE TABLE #TestTempTab (PrimaryKey int PRIMARY KEY, Col1 nchar );  
INSERT INTO #TestTempTab  
         SELECT * FROM TestPermTab;  
GO  
```  
  
 <span data-ttu-id="ab31f-129">Im vorherigen Beispiel verwendet die **tempdb** -Datenbank die Latin1_General_CS_AS-Sortierung, und `TestDB` und `TestTab.Col1` verwenden die `Estonian_CS_AS` -Sortierung.</span><span class="sxs-lookup"><span data-stu-id="ab31f-129">With the previous example, the **tempdb** database uses the Latin1_General_CS_AS collation, and `TestDB` and `TestTab.Col1` use the `Estonian_CS_AS` collation.</span></span> <span data-ttu-id="ab31f-130">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ab31f-130">For example:</span></span>  
  
```  
SELECT * FROM TestPermTab AS a INNER JOIN #TestTempTab on a.Col1 = #TestTempTab.Col1;  
```  
  
 <span data-ttu-id="ab31f-131">Da **tempdb** die Standardserversortierung und `TestPermTab.Col1` eine andere Sortierung verwendet, wird in SQL Server der folgende Fehler zurückgegeben: „Ein Sortierungskonflikt zwischen ‚Latin1_General_CI_AS_KS_WS‘ und ‚Estonian_CS_AS‘ im Gleich-Vorgang kann nicht aufgelöst werden.“</span><span class="sxs-lookup"><span data-stu-id="ab31f-131">Because **tempdb** uses the default server collation and `TestPermTab.Col1` uses a different collation, SQL Server returns this error: "Cannot resolve collation conflict between 'Latin1_General_CI_AS_KS_WS' and 'Estonian_CS_AS' in equal to operation."</span></span>  
  
 <span data-ttu-id="ab31f-132">Sie können den Fehler vermeiden, indem Sie stattdessen eine der folgenden Alternativen verwenden:</span><span class="sxs-lookup"><span data-stu-id="ab31f-132">To prevent the error, you can use one of the following alternatives:</span></span>  
  
-   <span data-ttu-id="ab31f-133">Geben Sie an, dass für die Spalte der temporären Tabelle die Standardsortierung der Benutzerdatenbank und nicht die Standardsortierung von **tempdb**verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ab31f-133">Specify that the temporary table column use the default collation of the user database, not **tempdb**.</span></span> <span data-ttu-id="ab31f-134">Auf diese Weise kann die temporäre Tabelle mit ähnlich formatierten Tabellen in mehreren Datenbanken arbeiten, wenn dies in dem System erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ab31f-134">This enables the temporary table to work with similarly formatted tables in multiple databases, if that is required of your system.</span></span>  
  
    ```  
    CREATE TABLE #TestTempTab  
       (PrimaryKey int PRIMARY KEY,  
        Col1 nchar COLLATE database_default  
       );  
    ```  
  
-   <span data-ttu-id="ab31f-135">Geben Sie die richtige Sortierung für die `#TestTempTab` -Spalte an:</span><span class="sxs-lookup"><span data-stu-id="ab31f-135">Specify the correct collation for the `#TestTempTab` column:</span></span>  
  
    ```  
    CREATE TABLE #TestTempTab  
       (PrimaryKey int PRIMARY KEY,  
        Col1 nchar COLLATE Estonian_CS_AS  
       );  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ab31f-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ab31f-136">See Also</span></span>  
 <span data-ttu-id="ab31f-137">[Festlegen oder Ändern der Server Sortierung](set-or-change-the-server-collation.md) </span><span class="sxs-lookup"><span data-stu-id="ab31f-137">[Set or Change the Server Collation](set-or-change-the-server-collation.md) </span></span>  
 <span data-ttu-id="ab31f-138">[Festlegen oder Ändern der Datenbanksortierung](set-or-change-the-database-collation.md) </span><span class="sxs-lookup"><span data-stu-id="ab31f-138">[Set or Change the Database Collation](set-or-change-the-database-collation.md) </span></span>  
 [<span data-ttu-id="ab31f-139">Collation and Unicode Support</span><span class="sxs-lookup"><span data-stu-id="ab31f-139">Collation and Unicode Support</span></span>](collation-and-unicode-support.md)  
  
  
