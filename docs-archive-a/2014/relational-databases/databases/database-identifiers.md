---
title: Datenbankbezeichner | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- regular identifiers [SQL Server]
- identifiers [SQL Server]
- names [SQL Server], identifiers
- identifiers [SQL Server], about identifiers
- SQL Server identifiers
- Transact-SQL identifiers
- database objects [SQL Server], names
ms.assetid: 171291bb-f57f-4ad1-8cea-0b092d5d150c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 347b20c12a0ac5edd82172741377617aa0fe12c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617113"
---
# <a name="database-identifiers"></a><span data-ttu-id="b6fcb-102">Datenbankbezeichner</span><span class="sxs-lookup"><span data-stu-id="b6fcb-102">Database Identifiers</span></span>
  <span data-ttu-id="b6fcb-103">Der Name eines Datenbankobjekts wird Bezeichner genannt.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-103">The database object name is referred to as its identifier.</span></span> <span data-ttu-id="b6fcb-104">Jedes Element in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kann über einen Bezeichner verfügen.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-104">Everything in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can have an identifier.</span></span> <span data-ttu-id="b6fcb-105">Hierzu gehören beispielsweise Server, Datenbanken und Datenbankobjekte wie Tabellen, Sichten, Spalten, Indizes, Trigger, Prozeduren, Einschränkungen und Regeln.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-105">Servers, databases, and database objects, such as tables, views, columns, indexes, triggers, procedures, constraints, and rules, can have identifiers.</span></span> <span data-ttu-id="b6fcb-106">Bezeichner werden für die meisten Objekte benötigt, sind jedoch bei einigen Objekten, z. B. Einschränkungen, optional.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-106">Identifiers are required for most objects, but are optional for some objects such as constraints.</span></span>  
  
 <span data-ttu-id="b6fcb-107">Der Bezeichner eines Objekts wird erstellt, wenn das Objekt definiert wird.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-107">An object identifier is created when the object is defined.</span></span> <span data-ttu-id="b6fcb-108">Der Bezeichner wird anschließend verwendet, um auf das Objekt zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-108">The identifier is then used to reference the object.</span></span> <span data-ttu-id="b6fcb-109">So erstellt beispielsweise die folgende Anweisung eine Tabelle mit dem Bezeichner `TableX`und zwei Spalten mit den Bezeichnern `KeyCol` und `Description`:</span><span class="sxs-lookup"><span data-stu-id="b6fcb-109">For example, the following statement creates a table with the identifier `TableX`, and two columns with the identifiers `KeyCol` and `Description`:</span></span>  
  
```  
CREATE TABLE TableX  
(KeyCol INT PRIMARY KEY, Description nvarchar(80))  
```  
  
 <span data-ttu-id="b6fcb-110">Die Tabelle enthält außerdem eine unbenannte Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-110">This table also has an unnamed constraint.</span></span> <span data-ttu-id="b6fcb-111">Die `PRIMARY KEY` -Einschränkung besitzt keinen Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-111">The `PRIMARY KEY` constraint has no identifier.</span></span>  
  
 <span data-ttu-id="b6fcb-112">Die Sortierung eines Bezeichners hängt von der Ebene ab, auf der er definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-112">The collation of an identifier depends on the level at which it is defined.</span></span> <span data-ttu-id="b6fcb-113">Bezeichnern von Objekten auf Instanzebene, wie z. B. Anmeldenamen und Datenbanknamen, wird die Standardsortierung der Instanz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-113">Identifiers of instance-level objects, such as logins and database names, are assigned the default collation of the instance.</span></span> <span data-ttu-id="b6fcb-114">Bezeichnern von Objekten innerhalb einer Datenbank, z. B. Tabellen, Sichten und Spaltennamen, wird die Standardsortierung der Datenbank zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-114">Identifiers of objects in a database, such as tables, views, and column names, are assigned the default collation of the database.</span></span> <span data-ttu-id="b6fcb-115">Beispielsweise können in einer Datenbank mit einer nach Groß-/Kleinschreibung unterscheidenden Sortierung zwei Tabellen mit gleichen Namen, die sich nur durch verschiedene Groß-/Kleinschreibung unterscheiden, erstellt werden; in einer Datenbank mit einer Sortierung ohne Unterscheidung nach Groß-/Kleinschreibung ist dies jedoch nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-115">For example, two tables with names that differ only in case can be created in a database that has case-sensitive collation, but cannot be created in a database that has case-insensitive collation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6fcb-116">Die Namen von Variablen oder die Parameter von Funktionen und gespeicherten Prozeduren müssen die Regeln für [!INCLUDE[tsql](../../includes/tsql-md.md)] -Bezeichner einhalten.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-116">The names of variables, or the parameters of functions and stored procedures must comply with the rules for [!INCLUDE[tsql](../../includes/tsql-md.md)] identifiers.</span></span>  
  
## <a name="classes-of-identifiers"></a><span data-ttu-id="b6fcb-117">Bezeichnerklassen</span><span class="sxs-lookup"><span data-stu-id="b6fcb-117">Classes of Identifiers</span></span>  
 <span data-ttu-id="b6fcb-118">Es gibt zwei Klassen von Bezeichnern:</span><span class="sxs-lookup"><span data-stu-id="b6fcb-118">There are two classes of identifiers:</span></span>  
  
 <span data-ttu-id="b6fcb-119">Reguläre Bezeichner</span><span class="sxs-lookup"><span data-stu-id="b6fcb-119">Regular identifiers</span></span>  
 <span data-ttu-id="b6fcb-120">Sie entsprechen den Regeln für das Format von Bezeichnern.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-120">Comply with the rules for the format of identifiers.</span></span> <span data-ttu-id="b6fcb-121">Reguläre Bezeichner sind nicht begrenzt, wenn sie in [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-121">Regular identifiers are not delimited when they are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
```  
SELECT *  
FROM TableX  
WHERE KeyCol = 124  
```  
  
 <span data-ttu-id="b6fcb-122">Begrenzungsbezeichner</span><span class="sxs-lookup"><span data-stu-id="b6fcb-122">Delimited identifiers</span></span>  
 <span data-ttu-id="b6fcb-123">Sie werden entweder in doppelte Anführungszeichen (") oder eckige Klammern ([ ]) eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-123">Are enclosed in double quotation marks (") or brackets ([ ]).</span></span> <span data-ttu-id="b6fcb-124">Bezeichner, die den Regeln für das Format von Bezeichnern entsprechen, können u. U. nicht begrenzt sein.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-124">Identifiers that comply with the rules for the format of identifiers might not be delimited.</span></span> <span data-ttu-id="b6fcb-125">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b6fcb-125">For example:</span></span>  
  
```  
SELECT *  
FROM [TableX]         --Delimiter is optional.  
WHERE [KeyCol] = 124  --Delimiter is optional.  
```  
  
 <span data-ttu-id="b6fcb-126">Bezeichner, die nicht allen Regeln für Bezeichner entsprechen, müssen in einer [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung begrenzt werden.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-126">Identifiers that do not comply with all the rules for identifiers must be delimited in a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="b6fcb-127">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b6fcb-127">For example:</span></span>  
  
```  
SELECT *  
FROM [My Table]      --Identifier contains a space and uses a reserved keyword.  
WHERE [order] = 10   --Identifier is a reserved keyword.  
```  
  
 <span data-ttu-id="b6fcb-128">Sowohl reguläre als auch Begrenzungsezeichner müssen zwischen 1 und 128 Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-128">Both regular and delimited identifiers must contain from 1 through 128 characters.</span></span> <span data-ttu-id="b6fcb-129">Bei lokalen temporären Tabellen darf der Bezeichner maximal 116 Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-129">For local temporary tables, the identifier can have a maximum of 116 characters.</span></span>  
  
## <a name="rules-for-regular-identifiers"></a><span data-ttu-id="b6fcb-130">Regeln für reguläre Bezeichner</span><span class="sxs-lookup"><span data-stu-id="b6fcb-130">Rules for Regular Identifiers</span></span>  
 <span data-ttu-id="b6fcb-131">Die Namen von Variablen, Funktionen und gespeicherten Prozeduren müssen den folgenden Regeln für [!INCLUDE[tsql](../../includes/tsql-md.md)] -Bezeichner entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-131">The names of variables, functions, and stored procedures must comply with the following rules for [!INCLUDE[tsql](../../includes/tsql-md.md)] identifiers.</span></span>  
  
1.  <span data-ttu-id="b6fcb-132">Das erste Zeichen muss eines der folgenden Zeichen sein:</span><span class="sxs-lookup"><span data-stu-id="b6fcb-132">The first character must be one of the following:</span></span>  
  
    -   <span data-ttu-id="b6fcb-133">Ein vom Unicode-Standard 3,2 definierter Buchstabe.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-133">A letter as defined by the Unicode Standard 3.2.</span></span> <span data-ttu-id="b6fcb-134">Die Unicode-Definition von Buchstaben enthält die lateinischen Buchstaben von a bis z und von A bis Z sowie Buchstaben anderer Sprachen.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-134">The Unicode definition of letters includes Latin characters from a through z, from A through Z, and also letter characters from other languages.</span></span>  
  
    -   <span data-ttu-id="b6fcb-135">Das Sonderzeichen Unterstrich (_), At-Zeichen (@) oder Nummernzeichen (#).</span><span class="sxs-lookup"><span data-stu-id="b6fcb-135">The underscore (_), at sign (@), or number sign (#).</span></span>  
  
         <span data-ttu-id="b6fcb-136">Bestimmte Sonderzeichen am Anfang eines Bezeichners haben in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]eine besondere Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-136">Certain symbols at the beginning of an identifier have special meaning in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b6fcb-137">Ein mit dem At-Zeichen beginnender regulärer Bezeichner bezeichnet immer eine lokale Variable oder einen lokalen Parameter und kann nicht als Name eines Objekts eines anderen Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-137">A regular identifier that starts with the at sign always denotes a local variable or parameter and cannot be used as the name of any other type of object.</span></span> <span data-ttu-id="b6fcb-138">Ein mit dem Nummernzeichen (#) beginnender Bezeichner steht für eine temporäre Tabelle oder Prozedur.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-138">An identifier that starts with a number sign denotes a temporary table or procedure.</span></span> <span data-ttu-id="b6fcb-139">Ein Bezeichner, der mit einem doppelten Nummernzeichen (##) beginnt, steht für ein globales temporäres Objekt.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-139">An identifier that starts with double number signs (##) denotes a global temporary object.</span></span> <span data-ttu-id="b6fcb-140">Das Nummernzeichen und das doppelte Nummernzeichen können zwar auch am Anfang von Namen von Objekten anderer Typen stehen, diese Vorgehensweise wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-140">Although the number sign or double number sign characters can be used to begin the names of other types of objects, we do not recommend this practice.</span></span>  
  
         <span data-ttu-id="b6fcb-141">Einige [!INCLUDE[tsql](../../includes/tsql-md.md)] -Funktionen haben Namen, die mit doppelten At-Zeichen beginnen (@@).</span><span class="sxs-lookup"><span data-stu-id="b6fcb-141">Some [!INCLUDE[tsql](../../includes/tsql-md.md)] functions have names that start with double at signs (@@).</span></span> <span data-ttu-id="b6fcb-142">Um Verwechslungen zu vermeiden, sollten Sie keine Namen verwenden, die mit einem @@ beginnen.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-142">To avoid confusion with these functions, you should not use names that start with @@.</span></span>  
  
2.  <span data-ttu-id="b6fcb-143">Als nachfolgende Zeichen können folgende Zeichen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="b6fcb-143">Subsequent characters can include the following:</span></span>  
  
    -   <span data-ttu-id="b6fcb-144">Im Unicode-Standard 3,2 definierte Buchstaben.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-144">Letters as defined in the Unicode Standard 3.2.</span></span>  
  
    -   <span data-ttu-id="b6fcb-145">Dezimalzahlen aus dem lateinischen Grundalphabet oder anderen nationalen Schriften.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-145">Decimal numbers from either Basic Latin or other national scripts.</span></span>  
  
    -   <span data-ttu-id="b6fcb-146">Das At-Zeichen, Dollar-Zeichen ($), Nummernzeichen oder Unterstrich-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-146">The at sign, dollar sign ($), number sign, or underscore.</span></span>  
  
3.  <span data-ttu-id="b6fcb-147">Der Bezeichner darf kein reserviertes [!INCLUDE[tsql](../../includes/tsql-md.md)] -Wort sein.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-147">The identifier must not be a [!INCLUDE[tsql](../../includes/tsql-md.md)] reserved word.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b6fcb-148">reserviert sowohl die groß- also auch die kleingeschriebene Version reservierter Wörter.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-148">reserves both the uppercase and lowercase versions of reserved words.</span></span> <span data-ttu-id="b6fcb-149">Beim Verwenden von Bezeichnern in [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen müssen alle Bezeichner, die diese Regeln nicht einhalten, durch doppelte Anführungszeichen oder eckige Klammern begrenzt werden.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-149">When identifiers are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, the identifiers that do not comply with these rules must be delimited by double quotation marks or brackets.</span></span> <span data-ttu-id="b6fcb-150">Welche Wörter reserviert werden, hängt vom Kompatibilitätsgrad der Datenbank ab.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-150">The words that are reserved depend on the database compatibility level.</span></span> <span data-ttu-id="b6fcb-151">Der Grad kann mithilfe der [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) -Anweisung festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-151">This level can be set by using the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) statement.</span></span>  
  
4.  <span data-ttu-id="b6fcb-152">Eingebettete Leerzeichen oder Sonderzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-152">Embedded spaces or special characters are not allowed.</span></span>  
  
5.  <span data-ttu-id="b6fcb-153">Ergänzende Zeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-153">Supplementary characters are not allowed.</span></span>  
  
 <span data-ttu-id="b6fcb-154">Beim Verwenden von Bezeichnern in [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen müssen alle Bezeichner, die diese Regeln nicht einhalten, durch doppelte Anführungszeichen oder eckige Klammern begrenzt werden.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-154">When identifiers are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, the identifiers that do not comply with these rules must be delimited by double quotation marks or brackets.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6fcb-155">Einige Regeln für das Format regulärer Bezeichner sind vom Kompatibilitätsgrad der Datenbank abhängig.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-155">Some rules for the format of regular identifiers depend on the database compatibility level.</span></span> <span data-ttu-id="b6fcb-156">Dieser Grad kann mithilfe von [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level)festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b6fcb-156">This level can be set by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6fcb-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6fcb-157">See Also</span></span>  
 <span data-ttu-id="b6fcb-158">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6fcb-158">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 <span data-ttu-id="b6fcb-159">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6fcb-159">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="b6fcb-160">[CREATE DEFAULT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-default-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6fcb-160">[CREATE DEFAULT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-default-transact-sql) </span></span>  
 <span data-ttu-id="b6fcb-161">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6fcb-161">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 <span data-ttu-id="b6fcb-162">[CREATE RULE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-rule-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6fcb-162">[CREATE RULE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-rule-transact-sql) </span></span>  
 <span data-ttu-id="b6fcb-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6fcb-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 <span data-ttu-id="b6fcb-164">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6fcb-164">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="b6fcb-165">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6fcb-165">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span></span>  
 <span data-ttu-id="b6fcb-166">[DEKLARIEREN SIE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6fcb-166">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="b6fcb-167">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6fcb-167">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span></span>  
 <span data-ttu-id="b6fcb-168">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6fcb-168">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="b6fcb-169">[Reserved Keywords &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reserved-keywords-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6fcb-169">[Reserved Keywords &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reserved-keywords-transact-sql) </span></span>  
 <span data-ttu-id="b6fcb-170">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6fcb-170">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="b6fcb-171">UPDATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b6fcb-171">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
