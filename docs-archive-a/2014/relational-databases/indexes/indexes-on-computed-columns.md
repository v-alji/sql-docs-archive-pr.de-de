---
title: Indizes in berechneten Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- computed columns, index creation
- index creation [SQL Server], computed columns
- imprecise columns
- persisted computed columns
- precise [SQL Server]
ms.assetid: 8d17ac9c-f3af-4bbb-9cc1-5cf647e994c4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2ecbca9e7838c4c9395a8bcb6e11351c40f7037f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725741"
---
# <a name="indexes-on-computed-columns"></a><span data-ttu-id="eab09-102">Indizes in berechneten Spalten</span><span class="sxs-lookup"><span data-stu-id="eab09-102">Indexes on Computed Columns</span></span>
  <span data-ttu-id="eab09-103">Sie können Indizes für berechnete Spalten definieren, sofern die folgenden Anforderungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="eab09-103">You can define indexes on computed columns as long as the following requirements are met:</span></span>  
  
-   <span data-ttu-id="eab09-104">Anforderungen hinsichtlich des Besitzes</span><span class="sxs-lookup"><span data-stu-id="eab09-104">Ownership requirements</span></span>  
  
-   <span data-ttu-id="eab09-105">Anforderungen hinsichtlich des Determinismus</span><span class="sxs-lookup"><span data-stu-id="eab09-105">Determinism requirements</span></span>  
  
-   <span data-ttu-id="eab09-106">Anforderungen hinsichtlich der Präzision</span><span class="sxs-lookup"><span data-stu-id="eab09-106">Precision requirements</span></span>  
  
-   <span data-ttu-id="eab09-107">Anforderungen hinsichtlich des Datentyps</span><span class="sxs-lookup"><span data-stu-id="eab09-107">Data type requirements</span></span>  
  
-   <span data-ttu-id="eab09-108">Anforderungen hinsichtlich der SET-Option</span><span class="sxs-lookup"><span data-stu-id="eab09-108">SET option requirements</span></span>  
  
 <span data-ttu-id="eab09-109">**Ownership Requirements**</span><span class="sxs-lookup"><span data-stu-id="eab09-109">**Ownership Requirements**</span></span>  
  
 <span data-ttu-id="eab09-110">Alle Funktionsverweise in der berechneten Spalte müssen denselben Besitzer wie die Tabelle aufweisen.</span><span class="sxs-lookup"><span data-stu-id="eab09-110">All function references in the computed column must have the same owner as the table.</span></span>  
  
 <span data-ttu-id="eab09-111">**Determinism Requirements**</span><span class="sxs-lookup"><span data-stu-id="eab09-111">**Determinism Requirements**</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="eab09-112">Ausdrücke gelten als deterministisch, wenn sie für eine bestimmte Gruppen von Eingaben stets dasselbe Ergebnis zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="eab09-112">Expressions are deterministic if they always return the same result for a specified set of inputs.</span></span> <span data-ttu-id="eab09-113">Die **IsDeterministic** -Eigenschaft der [COLUMNPROPERTY](/sql/t-sql/functions/columnproperty-transact-sql) -Funktion teilt mit, ob der Ausdruck einer berechneten Spalte ( *computed_column_expression* ) deterministisch ist.</span><span class="sxs-lookup"><span data-stu-id="eab09-113">The **IsDeterministic** property of the [COLUMNPROPERTY](/sql/t-sql/functions/columnproperty-transact-sql) function reports whether a *computed_column_expression* is deterministic.</span></span>  
  
 <span data-ttu-id="eab09-114">Der *computed_column_expression* muss deterministisch sein.</span><span class="sxs-lookup"><span data-stu-id="eab09-114">The *computed_column_expression* must be deterministic.</span></span> <span data-ttu-id="eab09-115">Ein *computed_column_expression* ist deterministisch, wenn mindestens eine der folgenden Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="eab09-115">A *computed_column_expression* is deterministic when one or more of the following is true:</span></span>  
  
-   <span data-ttu-id="eab09-116">Alle Funktionen, auf die der Ausdruck verweist, sind deterministisch und präzise.</span><span class="sxs-lookup"><span data-stu-id="eab09-116">All functions that are referenced by the expression are deterministic and precise.</span></span> <span data-ttu-id="eab09-117">Zu diesen Funktionen zählen benutzerdefinierte und integrierte Funktionen.</span><span class="sxs-lookup"><span data-stu-id="eab09-117">These functions include both user-defined and built-in functions.</span></span> <span data-ttu-id="eab09-118">Weitere Informationen finden Sie unter [Deterministic and Nondeterministic Functions](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span><span class="sxs-lookup"><span data-stu-id="eab09-118">For more information, see [Deterministic and Nondeterministic Functions](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span></span> <span data-ttu-id="eab09-119">Funktionen können unpräzise sein, wenn die berechnete Spalte als PERSISTED markiert ist.</span><span class="sxs-lookup"><span data-stu-id="eab09-119">Functions might be imprecise if the computed column is PERSISTED.</span></span> <span data-ttu-id="eab09-120">Weitere Informationen finden Sie unter [Erstellen von Indizes für persistente berechnete Spalten](#BKMK_persisted) nachfolgend in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="eab09-120">For more information, see [Creating Indexes on Persisted Computed Columns](#BKMK_persisted) later in this topic.</span></span>  
  
-   <span data-ttu-id="eab09-121">Alle Spalten, auf die der Ausdruck verweist, stammen aus der Tabelle, die die berechnete Spalte enthält.</span><span class="sxs-lookup"><span data-stu-id="eab09-121">All columns that are referenced in the expression come from the table that contains the computed column.</span></span>  
  
-   <span data-ttu-id="eab09-122">Kein Spaltenverweis ruft Daten aus mehreren Zeilen ab.</span><span class="sxs-lookup"><span data-stu-id="eab09-122">No column reference pulls data from multiple rows.</span></span> <span data-ttu-id="eab09-123">Beispielsweise hängen Aggregatfunktionen wie SUM oder AVG von Daten aus mehreren Zeilen ab, und ein *computed_column_expression* wäre dadurch nicht deterministisch.</span><span class="sxs-lookup"><span data-stu-id="eab09-123">For example, aggregate functions such as SUM or AVG depend on data from multiple rows and would make a *computed_column_expression* nondeterministic.</span></span>  
  
-   <span data-ttu-id="eab09-124">Der *computed_column_expression* kann weder auf Systemdaten noch auf Benutzerdaten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="eab09-124">The *computed_column_expression* has no system data access or user data access.</span></span>  
  
 <span data-ttu-id="eab09-125">Jede berechnete Spalte, die einen CLR-Ausdruck (Common Language Runtime) enthält, muss deterministisch und als PERSISTED markiert sein, bevor die Spalte indiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="eab09-125">Any computed column that contains a common language runtime (CLR) expression must be deterministic and marked PERSISTED before the column can be indexed.</span></span> <span data-ttu-id="eab09-126">Ausdrücke des CLR-benutzerdefinierten Typs sind in den Definitionen berechneter Spalten zulässig.</span><span class="sxs-lookup"><span data-stu-id="eab09-126">CLR user-defined type expressions are allowed in computed column definitions.</span></span> <span data-ttu-id="eab09-127">Berechnete Spalten, deren Typ ein CLR-benutzerdefinierter Typ ist, können indiziert werden, sofern der Typ vergleichbar ist.</span><span class="sxs-lookup"><span data-stu-id="eab09-127">Computed columns whose type is a CLR user-defined type can be indexed as long as the type is comparable.</span></span> <span data-ttu-id="eab09-128">Weitere Informationen finden Sie unter [Benutzerdefinierte CLR-Typen](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="eab09-128">For more information, see [CLR User-Defined Types](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eab09-129">Wenn Sie in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]auf Zeichenfolgenliterale des Date-Datentyps in indizierten berechneten Spalten verweisen, ist es ratsam, das Literal explizit in den gewünschten Datentyp zu konvertieren, indem Sie ein deterministisches Datenformat verwenden.</span><span class="sxs-lookup"><span data-stu-id="eab09-129">When you refer to string literals of the date data type in indexed computed columns in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], we recommend that you explicitly convert the literal to the date type that you want by using a deterministic date format style.</span></span> <span data-ttu-id="eab09-130">Eine Liste der deterministischen Datenformatstile finden Sie unter [CAST und CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eab09-130">For a list of the date format styles that are deterministic, see [CAST and CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span> <span data-ttu-id="eab09-131">Ausdrücke für die implizierte Konvertierung von Zeichenfolgen in date-Datentypen werden als nicht deterministisch bezeichnet, es sei denn, der Kompatibilitätsgrad der Datenbank ist auf 80 oder niedriger festgelegt.</span><span class="sxs-lookup"><span data-stu-id="eab09-131">Expressions that involve implicit conversion of character strings to date data types are considered nondeterministic, unless the database compatibility level is set to 80 or earlier.</span></span> <span data-ttu-id="eab09-132">Ursache hierfür ist, dass die Ergebnisse von den [LANGUAGE](/sql/t-sql/statements/set-language-transact-sql) - und [DATEFORMAT](/sql/t-sql/statements/set-dateformat-transact-sql) -Einstellungen der Serversitzung abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="eab09-132">This is because the results depend on the [LANGUAGE](/sql/t-sql/statements/set-language-transact-sql) and [DATEFORMAT](/sql/t-sql/statements/set-dateformat-transact-sql) settings of the server session.</span></span> <span data-ttu-id="eab09-133">Die Ergebnisse des Ausdrucks `CONVERT (datetime, '30 listopad 1996', 113)` hängen beispielsweise von der LANGUAGE-Einstellung ab, da die Zeichenfolge '`30 listopad 1996`' für verschiedene Monate in verschiedenen Sprachen steht.</span><span class="sxs-lookup"><span data-stu-id="eab09-133">For example, the results of the expression `CONVERT (datetime, '30 listopad 1996', 113)` depend on the LANGUAGE setting because the string '`30 listopad 1996`' means different months in different languages.</span></span> <span data-ttu-id="eab09-134">In ähnlicher Weise interpretiert `DATEADD(mm,3,'2000-12-01')`in dem Ausdruck [!INCLUDE[ssDE](../../../includes/ssde-md.md)] die Zeichenfolge `'2000-12-01'` basierend auf der DATEFORMAT-Einstellung.</span><span class="sxs-lookup"><span data-stu-id="eab09-134">Similarly, in the expression `DATEADD(mm,3,'2000-12-01')`, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] interprets the string `'2000-12-01'` based on the DATEFORMAT setting.</span></span>  
>   
>  <span data-ttu-id="eab09-135">Die implizierte Konvertierung von Nicht-Unicode-Zeichendaten zwischen Sortierungen wird auch als nicht deterministisch erachtet, wenn der Kompatibilitätsgrad nicht auf 80 oder niedriger festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="eab09-135">Implicit conversion of non-Unicode character data between collations is also considered nondeterministic, unless the compatibility level is set to 80 or earlier.</span></span>  
>   
>  <span data-ttu-id="eab09-136">Beträgt die Einstellung des Kompatibilitätsgrades der Datenbank 90, können Sie keine Indizes für berechnete Spalten erstellen, die diese Ausdrücke enthalten.</span><span class="sxs-lookup"><span data-stu-id="eab09-136">When the database compatibility level setting is 90, you cannot create indexes on computed columns that contain these expressions.</span></span> <span data-ttu-id="eab09-137">Vorhandene berechnete Spalten, die diese Ausdrücke aus einer aktualisierten Datenbank enthalten, sind jedoch verwaltbar.</span><span class="sxs-lookup"><span data-stu-id="eab09-137">However, existing computed columns that contain these expressions from an upgraded database are maintainable.</span></span> <span data-ttu-id="eab09-138">Bei Verwendung indizierter berechneter Spalten, die implizite Konvertierungen von Zeichenfolgen in Datumsangaben enthalten, sollten Sie sicherstellen, dass die LANGUAGE- und DATEFORMAT-Einstellungen in der Datenbank und den Anwendungen konsistent sind, um mögliche Beschädigungen der Indizes zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="eab09-138">If you use indexed computed columns that contain implicit string to date conversions, to avoid possible index corruption, make sure that the LANGUAGE and DATEFORMAT settings are consistent in your databases and applications.</span></span>  
  
 <span data-ttu-id="eab09-139">**Precision Requirements**</span><span class="sxs-lookup"><span data-stu-id="eab09-139">**Precision Requirements**</span></span>  
  
 <span data-ttu-id="eab09-140">Der *computed_column_expression* muss präzise sein.</span><span class="sxs-lookup"><span data-stu-id="eab09-140">The *computed_column_expression* must be precise.</span></span> <span data-ttu-id="eab09-141">Ein *computed_column_expression* ist präzise, wenn mindestens eine der folgenden Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="eab09-141">A *computed_column_expression* is precise when one or more of the following is true:</span></span>  
  
-   <span data-ttu-id="eab09-142">Es handelt sich um keinen Ausdruck des `float`- oder `real`-Datentyps.</span><span class="sxs-lookup"><span data-stu-id="eab09-142">It is not an expression of the `float` or `real` data types.</span></span>  
  
-   <span data-ttu-id="eab09-143">In der Definition des Ausdrucks wird kein `float`- oder `real`-Datentyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="eab09-143">It does not use a `float` or `real` data type in its definition.</span></span> <span data-ttu-id="eab09-144">Beispielsweise ist in der folgenden Anweisung die `y`-Spalte vom `int`-Datentyp und deterministisch, aber nicht präzise.</span><span class="sxs-lookup"><span data-stu-id="eab09-144">For example, in the following statement, column `y` is `int` and deterministic but not precise.</span></span>  
  
    ```  
    CREATE TABLE t2 (a int, b int, c int, x float,   
       y AS CASE x   
             WHEN 0 THEN a   
             WHEN 1 THEN b   
             ELSE c   
          END);  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="eab09-145">Jeder `float`- oder `real`-Ausdruck gilt als nicht präzise und kann nicht als Schlüssel eines Indexes verwendet werden; ein `float`- oder `real`-Ausdruck kann in einer indizierten Sicht, jedoch nicht als Schlüssel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eab09-145">Any `float` or `real` expression is considered imprecise and cannot be a key of an index; a `float` or `real` expression can be used in an indexed view but not as a key.</span></span> <span data-ttu-id="eab09-146">Dies gilt auch für berechnete Spalten.</span><span class="sxs-lookup"><span data-stu-id="eab09-146">This is true also for computed columns.</span></span> <span data-ttu-id="eab09-147">Jede Funktion, jeder Ausdruck oder jede benutzerdefinierte Funktion gilt als unpräzise, wenn Sie `float`- oder `real`-Ausdrücke enthält.</span><span class="sxs-lookup"><span data-stu-id="eab09-147">Any function, expression, or user-defined function is considered imprecise if it contains any `float` or `real` expressions.</span></span> <span data-ttu-id="eab09-148">Das gilt auch für logische (Vergleiche).</span><span class="sxs-lookup"><span data-stu-id="eab09-148">This includes logical ones (comparisons).</span></span>  
  
 <span data-ttu-id="eab09-149">Die **IsPrecise** -Eigenschaft der COLUMNPROPERTY-Funktion teilt mit, ob der Ausdruck einer berechneten Spalte ( *computed_column_expression* ) präzise ist.</span><span class="sxs-lookup"><span data-stu-id="eab09-149">The **IsPrecise** property of the COLUMNPROPERTY function reports whether a *computed_column_expression* is precise.</span></span>  
  
 <span data-ttu-id="eab09-150">**Datentyp Anforderungen**</span><span class="sxs-lookup"><span data-stu-id="eab09-150">**Data Type Requirements**</span></span>  
  
-   <span data-ttu-id="eab09-151">Der *computed_column_expression* , der für die berechnete Spalte definiert ist, kann nicht zu den `text` `ntext` Datentypen, oder ausgewertet werden `image` .</span><span class="sxs-lookup"><span data-stu-id="eab09-151">The *computed_column_expression* defined for the computed column cannot evaluate to the `text`, `ntext`, or `image` data types.</span></span>  
  
-   <span data-ttu-id="eab09-152">Berechnete Spalten, die aus den Datentypen `image`, `ntext`, `text`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)` und `xml` abgeleitet wurden, können indiziert werden, solange der Datentyp der berechneten Spalte als Indexschlüsselspalte zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="eab09-152">Computed columns derived from `image`, `ntext`, `text`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, and `xml` data types can be indexed as long as the computed column data type is allowable as an index key column.</span></span>  
  
-   <span data-ttu-id="eab09-153">Berechnete Spalten, die aus `image`-, `ntext`- und `text`-Datentypen abgeleitet sind, können Nichtschlüsselspalten (eingeschlossene Spalten) in einem nicht gruppierten Index sein, so lange der Datentyp der berechneten Spalte für Nichtschlüsseldatenspalten zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="eab09-153">Computed columns derived from `image`, `ntext`, and `text` data types can be nonkey (included) columns in a nonclustered index as long as the computed column data type is allowable as a nonkey index column.</span></span>  
  
 <span data-ttu-id="eab09-154">**Anforderungen hinsichtlich der SET-Option**</span><span class="sxs-lookup"><span data-stu-id="eab09-154">**SET Option Requirements**</span></span>  
  
-   <span data-ttu-id="eab09-155">Die ANSI_NULLS-Option auf Verbindungsebene muss auf ON festgelegt sein, wenn die CREATE TABLE- oder ALTER TABLE-Anweisung, die die berechnete Spalte definiert, ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eab09-155">The ANSI_NULLS connection-level option must be set to ON when the CREATE TABLE or ALTER TABLE statement that defines the computed column is executed.</span></span> <span data-ttu-id="eab09-156">Die [OBJECTPROPERTY](/sql/t-sql/functions/objectpropertyex-transact-sql) -Funktion meldet mithilfe der **IsAnsiNullsOn** -Eigenschaft, ob die Option auf ON festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="eab09-156">The [OBJECTPROPERTY](/sql/t-sql/functions/objectpropertyex-transact-sql) function reports whether the option is on through the **IsAnsiNullsOn** property.</span></span>  
  
-   <span data-ttu-id="eab09-157">Für die Verbindung, für die der Index erstellt wird, und für alle Verbindungen, die versuchen, INSERT-, UPDATE- oder DELETE-Anweisungen auszuführen, die Werte des Indexes ändern, müssen sechs SET-Optionen auf ON und eine SET-Option auf OFF festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="eab09-157">The connection on which the index is created, and all connections trying INSERT, UPDATE, or DELETE statements that will change values in the index, must have six SET options set to ON and one option set to OFF.</span></span> <span data-ttu-id="eab09-158">Der Optimierer ignoriert einen Index für eine berechnete Spalte für alle SELECT-Anweisungen, die von einer Verbindung ausgeführt werden, die diese Optionseinstellungen nicht aufweist.</span><span class="sxs-lookup"><span data-stu-id="eab09-158">The optimizer ignores an index on a computed column for any SELECT statement executed by a connection that does not have these same option settings.</span></span>  
  
    -   <span data-ttu-id="eab09-159">Die NUMERIC_ROUNDABORT-Option muss auf OFF festgelegt sein, und die folgenden Optionen müssen auf ON festgelegt sein:</span><span class="sxs-lookup"><span data-stu-id="eab09-159">The NUMERIC_ROUNDABORT option must be set to OFF, and the following options must be set to ON:</span></span>  
  
    -   <span data-ttu-id="eab09-160">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="eab09-160">ANSI_NULLS</span></span>  
  
    -   <span data-ttu-id="eab09-161">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="eab09-161">ANSI_PADDING</span></span>  
  
    -   <span data-ttu-id="eab09-162">ANSI_WARNINGS</span><span class="sxs-lookup"><span data-stu-id="eab09-162">ANSI_WARNINGS</span></span>  
  
    -   <span data-ttu-id="eab09-163">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="eab09-163">ARITHABORT</span></span>  
  
    -   <span data-ttu-id="eab09-164">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="eab09-164">CONCAT_NULL_YIELDS_NULL</span></span>  
  
    -   <span data-ttu-id="eab09-165">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="eab09-165">QUOTED_IDENTIFIER</span></span>  
  
     <span data-ttu-id="eab09-166">Durch Festlegen von ANSI_WARNINGS auf ON wird implizit ARITHABORT auf ON festgelegt, wenn der Kompatibilitätsgrad der Datenbank auf 90 oder höher festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="eab09-166">Setting ANSI_WARNINGS to ON implicitly sets ARITHABORT to ON when the database compatibility level is set to 90 or higher.</span></span>  
  
##  <a name="creating-indexes-on-persisted-computed-columns"></a><a name="BKMK_persisted"></a> <span data-ttu-id="eab09-167">Erstellen von Indizes für persistente berechnete Spalten</span><span class="sxs-lookup"><span data-stu-id="eab09-167">Creating Indexes on Persisted Computed Columns</span></span>  
 <span data-ttu-id="eab09-168">Sie können einen Index für eine berechnete Spalte erstellen, die mit einem deterministischen, jedoch unpräzisen Ausdruck definiert wird, wenn die Spalte in der CREATE TABLE- oder ALTER TABLE-Anweisung als PERSISTED markiert wurde.</span><span class="sxs-lookup"><span data-stu-id="eab09-168">You can create an index on a computed column that is defined with a deterministic, but imprecise, expression if the column is marked PERSISTED in the CREATE TABLE or ALTER TABLE statement.</span></span> <span data-ttu-id="eab09-169">Dies bedeutet, dass diese beibehaltenen [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Werte verwendet, wenn ein Index für die Spalte erstellt wird und wenn in einer Abfrage auf den Index verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="eab09-169">This means that the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] uses these persisted values when it creates an index on the column, and when the index is referenced in a query.</span></span> <span data-ttu-id="eab09-170">Diese Option ermöglicht es Ihnen, einen Index für eine berechnete Spalte zu erstellen [!INCLUDE[ssDE](../../../includes/dnprdnshort-md.md)] , wenn, sowohl deterministisch als auch präzise ist.</span><span class="sxs-lookup"><span data-stu-id="eab09-170">This option enables you to create an index on a computed column when [!INCLUDE[ssDE](../../../includes/dnprdnshort-md.md)], is both deterministic and precise.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="eab09-171">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="eab09-171">Related Content</span></span>  
 [<span data-ttu-id="eab09-172">COLUMNPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="eab09-172">COLUMNPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/columnproperty-transact-sql)  
  
  
