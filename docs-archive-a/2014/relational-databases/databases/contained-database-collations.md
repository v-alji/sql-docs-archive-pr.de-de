---
title: Enthaltene Datenbanksortierungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- contained database, collations
ms.assetid: 4b44f6b9-2359-452f-8bb1-5520f2528483
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2648dbedea7708c4f39c922c56bba96cf38b0c0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718244"
---
# <a name="contained-database-collations"></a><span data-ttu-id="e1371-102">Enthaltene Datenbanksortierungen</span><span class="sxs-lookup"><span data-stu-id="e1371-102">Contained Database Collations</span></span>
  <span data-ttu-id="e1371-103">Auf die Sortierreihenfolge und die Gleichheitssemantik von Textdaten wirken sich verschiedene Eigenschaften aus, u. a. die Berücksichtigung der Groß- und Kleinschreibung, die Berücksichtigung von Akzenten sowie die verwendete Basissprache.</span><span class="sxs-lookup"><span data-stu-id="e1371-103">Various properties affect the sort order and equality semantics of textual data, including case sensitivity, accent sensitivity, and the base language being used.</span></span> <span data-ttu-id="e1371-104">Diese Eigenschaften werden für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durch die ausgewählte Sortierung der Daten ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="e1371-104">These qualities are expressed to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through the choice of collation for the data.</span></span> <span data-ttu-id="e1371-105">Eine ausführliche Erläuterung zu Sortierungen finden Sie unter [Sortierung und Unicode-Unterstützung](../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="e1371-105">For a more in-depth discussion of collations themselves, see [Collation and Unicode Support](../collations/collation-and-unicode-support.md).</span></span>  
  
 <span data-ttu-id="e1371-106">Sortierungen gelten nicht nur für in Benutzertabellen gespeicherte Daten, sondern für jeden von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] behandelten Text, einschließlich Metadaten, temporäre Objekte, Variablennamen usw. Deren Behandlung variiert in eigenständigen und abhängigen Datenbanken</span><span class="sxs-lookup"><span data-stu-id="e1371-106">Collations apply not only to data stored in user tables, but to all text handled by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], including metadata, temporary objects, variable names, etc. The handling of these differs in contained and non-contained databases.</span></span> <span data-ttu-id="e1371-107">Diese Änderung wirkt sich nicht auf viele Benutzer aus. Stattdessen trägt sie zu Unabhängigkeit von Instanzen und Einheitlichkeit bei.</span><span class="sxs-lookup"><span data-stu-id="e1371-107">This change will not affect many users, but helps provide instance independence and uniformity.</span></span> <span data-ttu-id="e1371-108">Dies verursacht jedoch möglicherweise auch etwas Verwirrung sowie Probleme bei Sitzungen, in denen sowohl auf enthaltene als auch auf nicht enthaltene Datenbanken zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="e1371-108">But this may also cause some confusion, as well as problems for sessions that access both contained and non-contained databases.</span></span>  
  
 <span data-ttu-id="e1371-109">In diesem Thema wird das Wesen der Änderung erläutert. Zudem werden einige Bereiche beschrieben, in denen sie möglicherweise Probleme verursacht.</span><span class="sxs-lookup"><span data-stu-id="e1371-109">This topic clarifies the content of the change, and examines areas where the change may cause problems.</span></span>  
  
## <a name="non-contained-databases"></a><span data-ttu-id="e1371-110">Abhängige Datenbanken</span><span class="sxs-lookup"><span data-stu-id="e1371-110">Non-Contained Databases</span></span>  
 <span data-ttu-id="e1371-111">Alle Datenbanken weisen eine Standardsortierung auf, die beim Erstellen oder Ändern einer Datenbank festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e1371-111">All databases have a default collation (which can be set when creating or altering a database.</span></span> <span data-ttu-id="e1371-112">Diese Sortierung wird für sämtliche Metadaten in der Datenbank sowie als Standard für alle Zeichenfolgenspalten in der Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1371-112">This collation is used for all metadata in the database, as well as the default for all string columns within the database.</span></span> <span data-ttu-id="e1371-113">Benutzer können mit der `COLLATE`-Klausel für jede einzelne Spalte eine andere Sortierung auswählen.</span><span class="sxs-lookup"><span data-stu-id="e1371-113">Users can choose a different collation for any particular column by using the `COLLATE` clause.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="e1371-114">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="e1371-114">Example 1</span></span>  
 <span data-ttu-id="e1371-115">Wenn Sie z. B. in Peking arbeiten, kann eine chinesische Sortierung verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="e1371-115">For example, if we were working in Beijing, we might use a Chinese collation:</span></span>  
  
```sql  
ALTER DATABASE MyDB COLLATE Chinese_Simplified_Pinyin_100_CI_AS;  
```  
  
 <span data-ttu-id="e1371-116">Wenn nun eine Spalte erstellt wird, ist deren Standardsortierung diese chinesische Sortierung. Gegebenenfalls kann jedoch eine andere Sortierung ausgewählt werden:</span><span class="sxs-lookup"><span data-stu-id="e1371-116">Now if we create a column, its default collation will be this Chinese collation, but we can choose another one if we want:</span></span>  
  
```sql  
CREATE TABLE MyTable  
      (mycolumn1 nvarchar,  
      mycolumn2 nvarchar COLLATE Frisian_100_CS_AS);  
GO  
SELECT name, collation_name  
FROM sys.columns  
WHERE name LIKE 'mycolumn%' ;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```sql  
name            collation_name  
--------------- ----------------------------------  
mycolumn1       Chinese_Simplified_Pinyin_100_CI_AS  
mycolumn2       Frisian_100_CS_AS  
```  
  
 <span data-ttu-id="e1371-117">Dies erscheint relativ einfach, es treten jedoch mehrere Probleme auf.</span><span class="sxs-lookup"><span data-stu-id="e1371-117">This appears relatively simple, but several problems arise.</span></span> <span data-ttu-id="e1371-118">Da die Sortierung für eine Spalte von der Datenbank abhängt, in der die Tabelle erstellt wird, treten Probleme mit der Verwendung temporärer Tabellen auf, die in gespeichert werden `tempdb` .</span><span class="sxs-lookup"><span data-stu-id="e1371-118">Because the collation for a column is dependent on the database in which the table is created, problems arise with the use of temporary tables which are stored in `tempdb`.</span></span> <span data-ttu-id="e1371-119">Die Sortierung von `tempdb` entspricht in der Regel der Sortierung für die-Instanz, die nicht mit der Daten Bank Sortierung übereinstimmen muss.</span><span class="sxs-lookup"><span data-stu-id="e1371-119">The collation of `tempdb` usually matches the collation for the instance, which does not have to match the database collation.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="e1371-120">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="e1371-120">Example 2</span></span>  
 <span data-ttu-id="e1371-121">Betrachten Sie beispielsweise die obige (chinesische) Datenbank, wenn diese in einer Instanz mit der Sortierung **Latin1_General** verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="e1371-121">For example, consider the (Chinese) database above when used on an instance with a **Latin1_General** collation:</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max)) ;  
GO  
```  
  
 <span data-ttu-id="e1371-122">Auf den ersten Blick weisen diese beiden Tabellen dasselbe Schema auf. Da sich aber die Sortierungen der Datenbanken unterscheiden, sind die Werte tatsächlich nicht kompatibel:</span><span class="sxs-lookup"><span data-stu-id="e1371-122">At first glance, these two tables look like they have the same schema, but since the collations of the databases differ, the values are actually incompatible:</span></span>  
  
```  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="e1371-123">Meldung 468, Ebene 16, Status 9, Zeile 2</span><span class="sxs-lookup"><span data-stu-id="e1371-123">Msg 468, Level 16, State 9, Line 2</span></span>  
  
 <span data-ttu-id="e1371-124">Ein Sortierungskonflikt zwischen "Latin1_General_100_CI_AS_KS_WS_SC" und "Chinese_Simplified_Pinyin_100_CI_AS" im Equal To-Vorgang kann nicht aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e1371-124">Cannot resolve the collation conflict between "Latin1_General_100_CI_AS_KS_WS_SC" and Chinese_Simplified_Pinyin_100_CI_AS" in the equal to operation.</span></span>  
  
 <span data-ttu-id="e1371-125">Dies kann durch das explizite Sortieren der temporären Tabelle korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="e1371-125">We can fix this by explicitly collating the temporary table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e1371-126">erleichtert diesen Vorgang etwas, indem das `DATABASE_DEFAULT`-Schlüsselwort für die `COLLATE`-Klausel bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e1371-126">makes this somewhat easier by providing the `DATABASE_DEFAULT` keyword for the `COLLATE` clause.</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max) COLLATE DATABASE_DEFAULT);  
GO  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt ;  
```  
  
 <span data-ttu-id="e1371-127">Die Ausführung erfolgt nun ohne Fehler.</span><span class="sxs-lookup"><span data-stu-id="e1371-127">This now runs without error.</span></span>  
  
 <span data-ttu-id="e1371-128">Das sortierungsabhängige Verhalten ist auch bei Variablen zu beobachten.</span><span class="sxs-lookup"><span data-stu-id="e1371-128">We can also see collation-dependent behavior with variables.</span></span> <span data-ttu-id="e1371-129">Betrachten Sie die folgende Funktion:</span><span class="sxs-lookup"><span data-stu-id="e1371-129">Consider the following function:</span></span>  
  
```  
CREATE FUNCTION f(@x INT) RETURNS INT  
AS BEGIN   
      DECLARE @I INT = 1  
      DECLARE @?? INT = 2  
      RETURN @x * @i  
END;  
```  
  
 <span data-ttu-id="e1371-130">Dies ist eine relativ spezielle Funktion.</span><span class="sxs-lookup"><span data-stu-id="e1371-130">This is a rather peculiar function.</span></span> <span data-ttu-id="e1371-131">Bei einer Sortierung mit Unterscheidung nach Groß-/Kleinschreibung @i kann die in der return-Klausel weder an @I noch an @ binden??.</span><span class="sxs-lookup"><span data-stu-id="e1371-131">In a case-sensitive collation, the @i in the return clause cannot bind to either @I or @??.</span></span> <span data-ttu-id="e1371-132">Bei der Sortierung „Latin1_General“ ohne Berücksichtigung der Groß-/Kleinschreibung wird @i an @I gebunden, und die Funktion gibt 1 zurück.</span><span class="sxs-lookup"><span data-stu-id="e1371-132">In a case-insensitive Latin1_General collation, @i binds to @I, and the function returns 1.</span></span> <span data-ttu-id="e1371-133">Bei der türkischen Sortierung ohne Beachtung der Groß-/Kleinschreibung wird jedoch @i an @??, gebunden, und die Funktion gibt 2 zurück.</span><span class="sxs-lookup"><span data-stu-id="e1371-133">But in a case-insensitive Turkish collation, @i binds to @??, and the function returns 2.</span></span> <span data-ttu-id="e1371-134">Dies kann erhebliche Beschädigungen in einer Datenbank verursachen, bei der zwischen Instanzen mit unterschiedlichen Sortierungen gewechselt wird.</span><span class="sxs-lookup"><span data-stu-id="e1371-134">This can wreak havoc on a database that moves between instances with different collations.</span></span>  
  
## <a name="contained-databases"></a><span data-ttu-id="e1371-135">Eigenständige Datenbanken</span><span class="sxs-lookup"><span data-stu-id="e1371-135">Contained Databases</span></span>  
 <span data-ttu-id="e1371-136">Da eines der Entwurfsziele bei eigenständigen Datenbanken darin besteht, diese in sich abgeschlossen einzurichten, muss die Abhängigkeit von Instanzen und `tempdb`-Sortierungen abgetrennt werden.</span><span class="sxs-lookup"><span data-stu-id="e1371-136">Since a design objective of contained databases is to make them self-contained, the dependence on the instance and `tempdb` collations must be severed.</span></span> <span data-ttu-id="e1371-137">Hierzu wurde für eigenständige Datenbanken das Konzept der Katalogsortierung eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e1371-137">To do this, contained databases introduce the concept of the catalog collation.</span></span> <span data-ttu-id="e1371-138">Die Katalogsortierung wird für Systemmetadaten und vorübergehende Objekte verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1371-138">The catalog collation is used for system metadata and transient objects.</span></span> <span data-ttu-id="e1371-139">Einzelheiten hierzu finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="e1371-139">Details are provided below.</span></span>  
  
 <span data-ttu-id="e1371-140">In einer eigenständigen Datenbank ist die Katalogsortierung **Latin1_General_100_CI_AS_WS_KS_SC**.</span><span class="sxs-lookup"><span data-stu-id="e1371-140">In a contained database, the catalog collation **Latin1_General_100_CI_AS_WS_KS_SC**.</span></span> <span data-ttu-id="e1371-141">Diese Sortierung ist für alle eigenständigen Datenbanken in allen Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] identisch und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e1371-141">This collation is the same for all contained databases on all instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and cannot be changed.</span></span>  
  
 <span data-ttu-id="e1371-142">Die Datenbanksortierung wird beibehalten, sie wird jedoch nur für Benutzerdaten als Standardsortierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1371-142">The database collation is retained, but is only used as the default collation for user data.</span></span> <span data-ttu-id="e1371-143">Standardmäßig entspricht die Daten Bank Sortierung der Modelldaten Bank Sortierung, kann jedoch vom Benutzer `CREATE` `ALTER DATABASE` wie bei nicht enthaltenen Datenbanken durch einen-Befehl oder einen-Befehl geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e1371-143">By default, the database collation is equal to the model database collation, but can be changed by the user through a `CREATE` or `ALTER DATABASE` command as with non-contained databases.</span></span>  
  
 <span data-ttu-id="e1371-144">Das neue Schlüsselwort `CATALOG_DEFAULT` ist in der `COLLATE`-Klausel verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e1371-144">A new keyword, `CATALOG_DEFAULT`, is available in the `COLLATE` clause.</span></span> <span data-ttu-id="e1371-145">Diese wird als Verknüpfung zur aktuellen Sortierung der Metadaten in enthaltenen und nicht enthaltenen Datenbanken verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1371-145">This is used as a shortcut to the current collation of metadata in both contained and non-contained databases.</span></span> <span data-ttu-id="e1371-146">Das heißt, in einer nicht enthaltenen Datenbank gibt `CATALOG_DEFAULT` die aktuelle Datenbanksortierung zurück, da Metadaten in der Datenbanksortierung sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="e1371-146">That is, in a non-contained database, `CATALOG_DEFAULT` will return the current database collation, since metadata is collated in the database collation.</span></span> <span data-ttu-id="e1371-147">In einer enthaltenen Datenbank können sich diese zwei Werte unterscheiden, da der Benutzer die Datenbanksortierung ändern kann, sodass sie von der Katalogsortierung abweicht.</span><span class="sxs-lookup"><span data-stu-id="e1371-147">In a contained database, these two values may be different, since the user can change the database collation so that it does not match the catalog collation.</span></span>  
  
 <span data-ttu-id="e1371-148">Das Verhalten verschiedener Objekte in nicht enthaltenen und enthaltenen Datenbanken wird in dieser Tabelle zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="e1371-148">The behavior of various objects in both non-contained and contained databases is summarized in this table:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="e1371-149">**Element**</span><span class="sxs-lookup"><span data-stu-id="e1371-149">**Item**</span></span>|<span data-ttu-id="e1371-150">**Nicht enthaltene Datenbank**</span><span class="sxs-lookup"><span data-stu-id="e1371-150">**Non-Contained Database**</span></span>|<span data-ttu-id="e1371-151">**Enthaltene Datenbank**</span><span class="sxs-lookup"><span data-stu-id="e1371-151">**Contained Database**</span></span>|  
|<span data-ttu-id="e1371-152">Benutzerdaten (Standard)</span><span class="sxs-lookup"><span data-stu-id="e1371-152">User Data (default)</span></span>|<span data-ttu-id="e1371-153">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e1371-153">DATABASE_DEFAULT</span></span>|<span data-ttu-id="e1371-154">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e1371-154">DATABASE_DEFAULT</span></span>|  
|<span data-ttu-id="e1371-155">Temp-Daten (Standard)</span><span class="sxs-lookup"><span data-stu-id="e1371-155">Temp Data (default)</span></span>|<span data-ttu-id="e1371-156">TempDB-Sortierung</span><span class="sxs-lookup"><span data-stu-id="e1371-156">TempDB Collation</span></span>|<span data-ttu-id="e1371-157">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e1371-157">DATABASE_DEFAULT</span></span>|  
|<span data-ttu-id="e1371-158">Metadaten</span><span class="sxs-lookup"><span data-stu-id="e1371-158">Metadata</span></span>|<span data-ttu-id="e1371-159">DATABASE_DEFAULT/CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e1371-159">DATABASE_DEFAULT / CATALOG_DEFAULT</span></span>|<span data-ttu-id="e1371-160">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e1371-160">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="e1371-161">Temporäre Metadaten</span><span class="sxs-lookup"><span data-stu-id="e1371-161">Temporary Metadata</span></span>|<span data-ttu-id="e1371-162">TempDB-Sortierung</span><span class="sxs-lookup"><span data-stu-id="e1371-162">tempdb Collation</span></span>|<span data-ttu-id="e1371-163">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e1371-163">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="e1371-164">Variables</span><span class="sxs-lookup"><span data-stu-id="e1371-164">Variables</span></span>|<span data-ttu-id="e1371-165">Instanzsortierung</span><span class="sxs-lookup"><span data-stu-id="e1371-165">Instance Collation</span></span>|<span data-ttu-id="e1371-166">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e1371-166">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="e1371-167">Goto-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e1371-167">Goto Labels</span></span>|<span data-ttu-id="e1371-168">Instanzsortierung</span><span class="sxs-lookup"><span data-stu-id="e1371-168">Instance Collation</span></span>|<span data-ttu-id="e1371-169">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e1371-169">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="e1371-170">Cursornamen</span><span class="sxs-lookup"><span data-stu-id="e1371-170">Cursor Names</span></span>|<span data-ttu-id="e1371-171">Instanzsortierung</span><span class="sxs-lookup"><span data-stu-id="e1371-171">Instance Collation</span></span>|<span data-ttu-id="e1371-172">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e1371-172">CATALOG_DEFAULT</span></span>|  
  
 <span data-ttu-id="e1371-173">Im zuvor beschriebenen Beispiel für eine temporäre Tabelle ist ersichtlich, dass dieses Sortierverhalten bei den meisten Verwendungen temporärer Tabellen eine explizite `COLLATE`-Klausel überflüssig macht.</span><span class="sxs-lookup"><span data-stu-id="e1371-173">If we temp table example previously described, we can see that this collation behavior eliminates the need for an explicit `COLLATE` clause in most temp table uses.</span></span> <span data-ttu-id="e1371-174">In einer enthaltenen Datenbank wird dieser Code nun ohne Fehler ausgeführt, selbst wenn sich die Datenbanksortierung und die Instanzsortierung unterscheiden:</span><span class="sxs-lookup"><span data-stu-id="e1371-174">In a contained database, this code now runs without error, even if the database and instance collations differ:</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max));  
GO  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt ;  
```  
  
 <span data-ttu-id="e1371-175">Dies funktioniert, da sowohl `T1_txt` als auch `T2_txt` in der Datenbanksortierung der enthaltenen Datenbank sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="e1371-175">This works because both `T1_txt` and `T2_txt` are collated in the database collation of the contained database.</span></span>  
  
## <a name="crossing-between-contained-and-uncontained-contexts"></a><span data-ttu-id="e1371-176">Wechseln zwischen einem enthaltenen und einem nicht enthaltenen Kontext</span><span class="sxs-lookup"><span data-stu-id="e1371-176">Crossing Between Contained and Uncontained Contexts</span></span>  
 <span data-ttu-id="e1371-177">Solange sich eine Sitzung auf eine enthaltene Datenbank beschränkt, darf die Datenbank nicht verlassen werden, mit der eine Verbindung besteht.</span><span class="sxs-lookup"><span data-stu-id="e1371-177">As long as a session in a contained database remains contained, it must remain within the database to which it connected.</span></span> <span data-ttu-id="e1371-178">In diesem Fall ist das Verhalten sehr einfach.</span><span class="sxs-lookup"><span data-stu-id="e1371-178">In this case the behavior is very straightforward.</span></span> <span data-ttu-id="e1371-179">Wenn jedoch in einer Sitzung zwischen einem enthaltenen und einem nicht enthaltenen Kontext gewechselt wird, ist das Verhalten komplexer, da die beiden Regelsätze überbrückt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e1371-179">But if a session crosses between contained and non-contained contexts, the behavior becomes more complex, since the two sets of rules must be bridged.</span></span> <span data-ttu-id="e1371-180">Dies kann in einer teilweise enthaltenen Datenbank der Fall sein, da ein Benutzer mit `USE` auf eine andere Datenbank zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="e1371-180">This can happen in a partially-contained database, since a user may `USE` to another database.</span></span> <span data-ttu-id="e1371-181">In diesem Fall werden die Unterschiede zwischen den Sortierungsregeln gemäß dem folgenden Prinzip behandelt.</span><span class="sxs-lookup"><span data-stu-id="e1371-181">In this case, the difference in collation rules is handled by the following principle.</span></span>  
  
-   <span data-ttu-id="e1371-182">Das Sortierungsverhalten für einen Batch wird von der Datenbank bestimmt, in der der Batch beginnt.</span><span class="sxs-lookup"><span data-stu-id="e1371-182">The collation behavior for a batch is determined by the database in which the batch begins.</span></span>  
  
 <span data-ttu-id="e1371-183">Beachten Sie, dass diese Entscheidung getroffen wird, bevor Befehle ausgegeben werden (auch der anfängliche `USE`-Befehl).</span><span class="sxs-lookup"><span data-stu-id="e1371-183">Note that this decision is made before any commands are issued, including an initial `USE`.</span></span> <span data-ttu-id="e1371-184">Das heißt, wenn ein Batch in einer eigenständigen Datenbank beginnt, der erste Befehl jedoch ein `USE`-Befehl für eine abhängige Datenbank ist, wird dennoch das Sortierungsverhalten der eigenständigen Datenbank für den Batch verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1371-184">That is, if a batch begins in a contained database, but the first command is a `USE` to a non-contained database, the contained collation behavior will still be used for the batch.</span></span> <span data-ttu-id="e1371-185">Angesichts dessen kann beispielsweise ein Verweis auf eine Variable mehrere mögliche Ergebnisse haben:</span><span class="sxs-lookup"><span data-stu-id="e1371-185">Given this, a reference to a variable, for example, may have multiple possible outcomes:</span></span>  
  
-   <span data-ttu-id="e1371-186">Durch den Verweis kann genau eine Übereinstimmung gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="e1371-186">The reference may find exactly one match.</span></span> <span data-ttu-id="e1371-187">In diesem Fall funktioniert der Verweis ohne Fehler.</span><span class="sxs-lookup"><span data-stu-id="e1371-187">In this case, the reference will work without error.</span></span>  
  
-   <span data-ttu-id="e1371-188">Durch den Verweis wird möglicherweise keine Übereinstimmung in der aktuellen Sortierung gefunden, obwohl zuvor eine vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="e1371-188">The reference may not find a match in the current collation where there was one before.</span></span> <span data-ttu-id="e1371-189">Dadurch wird ein Fehler ausgelöst, der angibt, dass die Variable nicht vorhanden ist, auch wenn diese offensichtlich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e1371-189">This will raise an error indicating that the variable does not exist, even though it was apparently created.</span></span>  
  
-   <span data-ttu-id="e1371-190">Durch den Verweis können mehrere Übereinstimmungen gefunden werden, die sich ursprünglich voneinander unterschieden haben.</span><span class="sxs-lookup"><span data-stu-id="e1371-190">The reference may find multiple matches that were originally distinct.</span></span> <span data-ttu-id="e1371-191">Auch hierdurch wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e1371-191">This will also raise an error.</span></span>  
  
 <span data-ttu-id="e1371-192">Dies wird im Folgenden anhand einiger Beispiele veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e1371-192">We'll illustrate this with a few examples.</span></span> <span data-ttu-id="e1371-193">Dabei wird angenommen, dass eine teilweise eigenständige Datenbank mit dem Namen `MyCDB` vorhanden ist, deren Datenbanksortierung auf die Standardsortierung **Latin1_General_100_CI_AS_WS_KS_SC**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e1371-193">For these we assume there is a partially-contained database named `MyCDB` with its database collation set to the default collation, **Latin1_General_100_CI_AS_WS_KS_SC**.</span></span> <span data-ttu-id="e1371-194">Es wird angenommen, dass die Instanzsortierung `Latin1_General_100_CS_AS_WS_KS_SC` ist.</span><span class="sxs-lookup"><span data-stu-id="e1371-194">We assume that the instance collation is `Latin1_General_100_CS_AS_WS_KS_SC`.</span></span> <span data-ttu-id="e1371-195">Die beiden Sortierungen unterscheiden sich nur hinsichtlich der Berücksichtigung der Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="e1371-195">The two collations differ only in case sensitivity.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="e1371-196">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="e1371-196">Example 1</span></span>  
 <span data-ttu-id="e1371-197">Im folgenden Beispiel wird der Fall veranschaulicht, bei dem durch den Verweis genau eine Übereinstimmung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="e1371-197">The following example illustrates the case where the reference finds exactly one match.</span></span>  
  
```  
USE MyCDB;  
GO  
  
CREATE TABLE #a(x int);  
INSERT INTO #a VALUES(1);  
GO  
  
USE master;  
GO  
  
SELECT * FROM #a;  
GO  
  
Results:  
  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
x  
-----------  
1  
```  
  
 <span data-ttu-id="e1371-198">In diesem Fall wird vom erkannten #a eine Bindung sowohl mit der Katalogsortierung ohne Berücksichtigung der Groß- und Kleinschreibung als auch mit der Instanzsortierung mit Berücksichtigung der Groß- und Kleinschreibung hergestellt, und der Code wird fehlerfrei ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e1371-198">In this case, the identified #a binds in both the case-insensitive catalog collation and the case-sensitive instance collation, and the code works.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="e1371-199">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="e1371-199">Example 2</span></span>  
 <span data-ttu-id="e1371-200">Im folgenden Beispiel wird der Fall veranschaulicht, in dem durch den Verweis keine Übereinstimmung in der aktuellen Sortierung gefunden wird, wo zuvor eine Übereinstimmung vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="e1371-200">The following example illustrates the case where the reference does not find a match in the current collation where there was one before.</span></span>  
  
```  
USE MyCDB;  
GO  
  
CREATE TABLE #a(x int);  
INSERT INTO #A VALUES(1);  
GO  
```  
  
 <span data-ttu-id="e1371-201">Hier wird eine Bindung von "#A" an "#a" in der Standardsortierung ohne Berücksichtigung der Groß- und Kleinschreibung hergestellt, und die Einfügung funktioniert.</span><span class="sxs-lookup"><span data-stu-id="e1371-201">Here, the #A binds to #a in the case-insensitive default collation, and the insert works,</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
(1 row(s) affected)  
```  
  
 <span data-ttu-id="e1371-202">Wenn jedoch das Skript fortgesetzt wird...</span><span class="sxs-lookup"><span data-stu-id="e1371-202">But if we continue the script...</span></span>  
  
```  
USE master;  
GO  
  
SELECT * FROM #A;  
GO  
```  
  
 <span data-ttu-id="e1371-203">Beim Versuch, eine Bindung an #A in der Instanzsortierung mit Berücksichtigung der Groß- und Kleinschreibung herzustellen, wird ein Fehler ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="e1371-203">We get an error trying to bind to #A in the case-sensitive instance collation;</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="e1371-204">Meldung 208, Ebene 16, Status 0, Zeile 2</span><span class="sxs-lookup"><span data-stu-id="e1371-204">Msg 208, Level 16, State 0, Line 2</span></span>  
  
 <span data-ttu-id="e1371-205">Ungültiger Objektname '#A'.</span><span class="sxs-lookup"><span data-stu-id="e1371-205">Invalid object name '#A'.</span></span>  
  
### <a name="example-3"></a><span data-ttu-id="e1371-206">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="e1371-206">Example 3</span></span>  
 <span data-ttu-id="e1371-207">Im folgenden Beispiel wird der Fall veranschaulicht, wo durch den Verweis mehrere Übereinstimmungen gefunden werden, die sich ursprünglich voneinander unterschieden haben.</span><span class="sxs-lookup"><span data-stu-id="e1371-207">The following example illustrates the case where the reference finds multiple matches that were originally distinct.</span></span> <span data-ttu-id="e1371-208">Zunächst beginnen wir mit `tempdb` (mit der gleichen Sortierung wie unsere-Instanz) und führen die folgenden Anweisungen aus.</span><span class="sxs-lookup"><span data-stu-id="e1371-208">First, we start in `tempdb` (which has the same case-sensitive collation as our instance) and execute the following statements.</span></span>  
  
```  
USE tempdb;  
GO  
  
CREATE TABLE #a(x int);  
GO  
CREATE TABLE #A(x int);  
GO  
INSERT INTO #a VALUES(1);  
GO  
INSERT INTO #A VALUES(2);  
GO  
```  
  
 <span data-ttu-id="e1371-209">Diese Ausführung ist erfolgreich, da die Tabellen in dieser Sortierung eindeutig sind:</span><span class="sxs-lookup"><span data-stu-id="e1371-209">This succeeds, since the tables are distinct in this collation:</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
(1 row(s) affected)  
(1 row(s) affected)  
```  
  
 <span data-ttu-id="e1371-210">Beim Wechseln in die enthaltene Datenbank wird jedoch festgestellt, dass keine Bindungen an diese Tabellen hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="e1371-210">If we move into our contained database, however, we find that we can no longer bind to these tables.</span></span>  
  
```  
USE MyCDB;  
GO  
SELECT * FROM #a;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="e1371-211">Meldung 12800, Ebene 16, Status 1, Zeile 2</span><span class="sxs-lookup"><span data-stu-id="e1371-211">Msg 12800, Level 16, State 1, Line 2</span></span>  
  
 <span data-ttu-id="e1371-212">Der Verweis auf den Namen '#a' der temporären Tabelle ist mehrdeutig und kann nicht aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e1371-212">The reference to temp table name '#a' is ambiguous and cannot be resolved.</span></span> <span data-ttu-id="e1371-213">Verwenden Sie entweder '#a' oder '#A'.</span><span class="sxs-lookup"><span data-stu-id="e1371-213">Possible candidates are '#a' and '#A'.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="e1371-214">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="e1371-214">Conclusion</span></span>  
 <span data-ttu-id="e1371-215">Das Sortierungsverhalten enthaltener Datenbanken unterscheidet sich leicht von dem nicht enthaltener Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="e1371-215">The collation behavior of contained databases differs subtly from that in non-contained databases.</span></span> <span data-ttu-id="e1371-216">Dieses Verhalten ist im Allgemeinen vorteilhaft und trägt zu Unabhängigkeit von Instanzen sowie Einfachheit bei.</span><span class="sxs-lookup"><span data-stu-id="e1371-216">This behavior is generally beneficial, providing instance-independence and simplicity.</span></span> <span data-ttu-id="e1371-217">Für einige Benutzer können Probleme auftreten, insbesondere dann, wenn in einer Sitzung sowohl auf enthaltene als auch auf nicht enthaltene Datenbanken zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="e1371-217">Some users may have issues, particularly when a session accesses both contained and non-contained databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1371-218">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1371-218">See Also</span></span>  
 [<span data-ttu-id="e1371-219">Eigenständige Datenbanken</span><span class="sxs-lookup"><span data-stu-id="e1371-219">Contained Databases</span></span>](contained-databases.md)  
  
  
