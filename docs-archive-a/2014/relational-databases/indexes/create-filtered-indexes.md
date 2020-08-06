---
title: Erstellen gefilterter Indizes | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- filtered indexes [SQL Server], about filtered indexes
- designing indexes [SQL Server], filtered
- filtered indexes [SQL Server]
- nonclustered indexes [SQL Server], filtered
- indexes [SQL Server], filtered
ms.assetid: 25e1fcc5-45d7-4c53-8c79-5493dfaa1c74
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 77cf641ca84181496f26a995244029d0525ade63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724642"
---
# <a name="create-filtered-indexes"></a><span data-ttu-id="5b03c-102">Erstellen gefilterter Indizes</span><span class="sxs-lookup"><span data-stu-id="5b03c-102">Create Filtered Indexes</span></span>
  <span data-ttu-id="5b03c-103">In diesem Thema wird beschrieben, wie ein gefilterter Index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5b03c-103">This topic describes how to create a filtered index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5b03c-104">Ein gefilterter Index ist ein optimierter nicht gruppierter Index, der sich besonders für Abfragen eignet, bei denen aus einer fest definierten Teilmenge von Daten ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="5b03c-104">A filtered index is an optimized nonclustered index especially suited to cover queries that select from a well-defined subset of data.</span></span> <span data-ttu-id="5b03c-105">Dieser verwendet ein Filterprädikat, um einen Teil der Zeilen in der Tabelle zu indizieren.</span><span class="sxs-lookup"><span data-stu-id="5b03c-105">It uses a filter predicate to index a portion of rows in the table.</span></span> <span data-ttu-id="5b03c-106">Mit einem sorgfältig entworfenen gefilterten Index können im Vergleich zu Tabellenindizes die Abfrageleistung verbessert und der Aufwand für die Indexverwaltung und die Indexspeicherung reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="5b03c-106">A well-designed filtered index can improve query performance as well as reduce index maintenance and storage costs compared with full-table indexes.</span></span>  
  
 <span data-ttu-id="5b03c-107">Gefilterte Indizes können gegenüber Tabellenindizes folgende Vorteile bieten:</span><span class="sxs-lookup"><span data-stu-id="5b03c-107">Filtered indexes can provide the following advantages over full-table indexes:</span></span>  
  
-   <span data-ttu-id="5b03c-108">**Verbesserte Abfrageleistung und Planqualität**</span><span class="sxs-lookup"><span data-stu-id="5b03c-108">**Improved query performance and plan quality**</span></span>  
  
     <span data-ttu-id="5b03c-109">Mit einem sorgfältig entworfenen gefilterten Index wird die Abfrageleistung und die Ausführungsplanqualität verbessert, da dieser kleiner ist als ein nicht gruppierter Tabellenindex und mit gefilterten Statistiken arbeitet.</span><span class="sxs-lookup"><span data-stu-id="5b03c-109">A well-designed filtered index improves query performance and execution plan quality because it is smaller than a full-table nonclustered index and has filtered statistics.</span></span> <span data-ttu-id="5b03c-110">Die gefilterten Statistiken sind genauer als Tabellenstatistiken, da diese nur die Zeilen im gefilterten Index umfassen.</span><span class="sxs-lookup"><span data-stu-id="5b03c-110">The filtered statistics are more accurate than full-table statistics because they cover only the rows in the filtered index.</span></span>  
  
-   <span data-ttu-id="5b03c-111">**Reduzierter Aufwand bei der Indexverwaltung**</span><span class="sxs-lookup"><span data-stu-id="5b03c-111">**Reduced index maintenance costs**</span></span>  
  
     <span data-ttu-id="5b03c-112">Ein Index wird nur beibehalten, wenn DML-Anweisungen (Data Manipulation Language) die Daten im Index beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="5b03c-112">An index is maintained only when data manipulation language (DML) statements affect the data in the index.</span></span> <span data-ttu-id="5b03c-113">Ein gefilterter Index reduziert im Vergleich zu einem nicht gruppierten Tabellenindex den Aufwand für die Indexverwaltung, da dieser kleiner ist und nur beibehalten wird, wenn die Daten im Index geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5b03c-113">A filtered index reduces index maintenance costs compared with a full-table nonclustered index because it is smaller and is only maintained when the data in the index is changed.</span></span> <span data-ttu-id="5b03c-114">Eine große Anzahl von gefilterten Indizes ist insbesondere dann von Vorteil, wenn diese Daten enthalten, die nur selten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5b03c-114">It is possible to have a large number of filtered indexes, especially when they contain data that is changed infrequently.</span></span> <span data-ttu-id="5b03c-115">Ebenso reduziert die geringere Indexgröße den Aufwand für das Aktualisieren der Statistiken, wenn ein gefilterter Index nur die häufig geänderten Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="5b03c-115">Similarly, if a filtered index contains only the frequently modified data, the smaller size of the index reduces the cost of updating the statistics.</span></span>  
  
-   <span data-ttu-id="5b03c-116">**Reduzierter Aufwand bei der Indexspeicherung**</span><span class="sxs-lookup"><span data-stu-id="5b03c-116">**Reduced index storage costs**</span></span>  
  
     <span data-ttu-id="5b03c-117">Ein gefilterter Index kann den Speicherplatzbedarf von nicht gruppierten Indizes reduzieren, wenn ein Tabellenindex nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="5b03c-117">Creating a filtered index can reduce disk storage for nonclustered indexes when a full-table index is not necessary.</span></span> <span data-ttu-id="5b03c-118">Sie können einen nicht gruppierten Tabellenindex durch mehrere gefilterte Indizes ersetzen, ohne damit die Speicherplatzanforderungen wesentlich zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="5b03c-118">You can replace a full-table nonclustered index with multiple filtered indexes without significantly increasing the storage requirements.</span></span>  
  
 <span data-ttu-id="5b03c-119">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="5b03c-119">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5b03c-120">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="5b03c-120">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5b03c-121">Entwurfsaspekte</span><span class="sxs-lookup"><span data-stu-id="5b03c-121">Design Considerations</span></span>](#Design)  
  
     [<span data-ttu-id="5b03c-122">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5b03c-122">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5b03c-123">Security</span><span class="sxs-lookup"><span data-stu-id="5b03c-123">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5b03c-124">**So erstellen Sie einen gefilterten Index mithilfe von:**</span><span class="sxs-lookup"><span data-stu-id="5b03c-124">**To create a filtered index, using:**</span></span>  
  
     [<span data-ttu-id="5b03c-125">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b03c-125">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5b03c-126">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b03c-126">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5b03c-127">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="5b03c-127">Before You Begin</span></span>  
  
###  <a name="design-considerations"></a><a name="Design"></a> <span data-ttu-id="5b03c-128">Entwurfsaspekte</span><span class="sxs-lookup"><span data-stu-id="5b03c-128">Design Considerations</span></span>  
  
-   <span data-ttu-id="5b03c-129">Wenn eine Spalte nur wenig relevante Werte für Abfragen aufweist, können Sie für die Teilmenge der Werte einen gefilterten Index erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b03c-129">When a column only has a small number of relevant values for queries, you can create a filtered index on the subset of values.</span></span> <span data-ttu-id="5b03c-130">Wenn beispielsweise die Werte in einer Spalte größtenteils NULL sind und die Abfrage nur die Werte ungleich NULL berücksichtigt, können Sie für die Datenzeilen mit den Werten ungleich NULL einen gefilterten Index erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b03c-130">For example, when the values in a column are mostly NULL and the query selects only from the non-NULL values, you can create a filtered index for the non-NULL data rows.</span></span> <span data-ttu-id="5b03c-131">Der resultierende Index ist kleiner und verursacht weniger Verwaltungsaufwand als ein nicht gruppierter Tabellenindex, der für dieselben Schlüsselspalten festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="5b03c-131">The resulting index will be smaller and cost less to maintain than a full-table nonclustered index defined on the same key columns.</span></span>  
  
-   <span data-ttu-id="5b03c-132">Wenn eine Tabelle heterogene Datenzeilen enthält, können Sie einen gefilterten Index für eine oder mehrere Datenkategorien erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b03c-132">When a table has heterogeneous data rows, you can create a filtered index for one or more categories of data.</span></span> <span data-ttu-id="5b03c-133">Dies kann die Leistung der Abfragen auf diesen Datenzeilen verbessern, indem es den Fokus einer Abfrage auf einen bestimmten Bereich der Tabelle eingrenzt.</span><span class="sxs-lookup"><span data-stu-id="5b03c-133">This can improve the performance of queries on these data rows by narrowing the focus of a query to a specific area of the table.</span></span> <span data-ttu-id="5b03c-134">Auch hier ist der resultierende Index kleiner und verursacht weniger Verwaltungsaufwand als ein nicht gruppierter Tabellenindex.</span><span class="sxs-lookup"><span data-stu-id="5b03c-134">Again, the resulting index will be smaller and cost less to maintain than a full-table nonclustered index.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5b03c-135">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5b03c-135">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5b03c-136">Sie können keinen gefilterten Index für eine Sicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b03c-136">You cannot create a filtered index on a view.</span></span> <span data-ttu-id="5b03c-137">Der Abfrageoptimierer kann jedoch von einem für eine Tabelle definierten gefilterten Index profitieren, auf den in einer Sicht verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5b03c-137">However, the query optimizer can benefit from a filtered index defined on a table that is referenced in a view.</span></span> <span data-ttu-id="5b03c-138">Der Abfrageoptimierer berücksichtigt einen gefilterten Index für eine Abfrage, die aus einer Sicht auswählt, wenn die Ergebnisse der Abfrage korrekt sind.</span><span class="sxs-lookup"><span data-stu-id="5b03c-138">The query optimizer considers a filtered index for a query that selects from a view if the query results will be correct.</span></span>  
  
-   <span data-ttu-id="5b03c-139">Gefilterte Indizes haben die folgenden Vorteile gegenüber indizierten Sichten:</span><span class="sxs-lookup"><span data-stu-id="5b03c-139">Filtered indexes have the following advantages over indexed views:</span></span>  
  
    -   <span data-ttu-id="5b03c-140">Reduzierter Aufwand bei der Indexverwaltung.</span><span class="sxs-lookup"><span data-stu-id="5b03c-140">Reduced index maintenance costs.</span></span> <span data-ttu-id="5b03c-141">Im Vergleich zu einer indizierten Sicht benötigt der Abfrageprozessor weniger CPU-Ressourcen, um einen gefilterten Index zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5b03c-141">For example, the query processor uses fewer CPU resources to update a filtered index than an indexed view.</span></span>  
  
    -   <span data-ttu-id="5b03c-142">Verbesserte Planqualität.</span><span class="sxs-lookup"><span data-stu-id="5b03c-142">Improved plan quality.</span></span> <span data-ttu-id="5b03c-143">Während der Abfragekompilierung wählt der Abfrageoptimierer in vielen Situationen bevorzugt einen gefilterten Index anstelle der äquivalenten indizierten Sicht aus.</span><span class="sxs-lookup"><span data-stu-id="5b03c-143">For example, during query compilation, the query optimizer considers using a filtered index in more situations than the equivalent indexed view.</span></span>  
  
    -   <span data-ttu-id="5b03c-144">Neuerstellung von online geschalteten Indizes.</span><span class="sxs-lookup"><span data-stu-id="5b03c-144">Online index rebuilds.</span></span> <span data-ttu-id="5b03c-145">Sie können gefilterte Indizes neu erstellen, während die Indizes für Abfragen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5b03c-145">You can rebuild filtered indexes while they are available for queries.</span></span> <span data-ttu-id="5b03c-146">Die Neuerstellung von online geschalteten Indizes wird bei indizierten Sichten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5b03c-146">Online index rebuilds are not supported for indexed views.</span></span> <span data-ttu-id="5b03c-147">Weitere Informationen finden Sie unter der REBUILD-Option für [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5b03c-147">For more information, see the REBUILD option for [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
    -   <span data-ttu-id="5b03c-148">Nicht eindeutige Indizes</span><span class="sxs-lookup"><span data-stu-id="5b03c-148">Non-unique indexes.</span></span> <span data-ttu-id="5b03c-149">Gefilterte Indizes können nicht eindeutig sein, wohingegen indizierte Sichten eindeutig sein müssen.</span><span class="sxs-lookup"><span data-stu-id="5b03c-149">Filtered indexes can be non-unique, whereas indexed views must be unique.</span></span>  
  
-   <span data-ttu-id="5b03c-150">Gefilterte Indizes werden für eine Tabelle definiert und unterstützen nur einfache Vergleichsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="5b03c-150">Filtered indexes are defined on one table and only support simple comparison operators.</span></span> <span data-ttu-id="5b03c-151">Wenn Sie einen Filterausdruck benötigen, der auf mehrere Tabellen verweist oder eine komplexe Logik aufweist, sollten Sie eine Sicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b03c-151">If you need a filter expression that references multiple tables or has complex logic, you should create a view.</span></span>  
  
-   <span data-ttu-id="5b03c-152">Eine Spalte im gefilterten Indexausdruck muss in der Definition des gefilterten Indexes keine Schlüsselspalte oder eingeschlossene Spalte sein, wenn der gefilterte Indexausdruck dem Abfrageprädikat entspricht und die Abfrage die Spalte im gefilterten Indexausdruck mit den Abfrageergebnissen nicht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5b03c-152">A column in the filtered index expression does not need to be a key or included column in the filtered index definition if the filtered index expression is equivalent to the query predicate and the query does not return the column in the filtered index expression with the query results.</span></span>  
  
-   <span data-ttu-id="5b03c-153">Eine Spalte im gefilterten Indexausdruck sollte in der Definition des gefilterten Indexes eine Schlüsselspalte oder eingeschlossene Spalte sein, wenn das Abfrageprädikat die Spalte in einem Vergleich verwendet, der nicht dem gefilterten Indexausdruck entspricht.</span><span class="sxs-lookup"><span data-stu-id="5b03c-153">A column in the filtered index expression should be a key or included column in the filtered index definition if the query predicate uses the column in a comparison that is not equivalent to the filtered index expression.</span></span>  
  
-   <span data-ttu-id="5b03c-154">Eine Spalte im gefilterten Indexausdruck sollte in der Definition des gefilterten Indexes eine Schlüsselspalte oder eingeschlossene Spalte sein, wenn die Spalte im Abfrageresultset enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="5b03c-154">A column in the filtered index expression should be a key or included column in the filtered index definition if the column is in the query result set.</span></span>  
  
-   <span data-ttu-id="5b03c-155">Der Schlüssel des gruppierten Indexes für die Tabelle muss in der Definition des gefilterten Indexes keine Schlüsselspalte oder eingeschlossene Spalte sein.</span><span class="sxs-lookup"><span data-stu-id="5b03c-155">The clustered index key of the table does not need to be a key or included column in the filtered index definition.</span></span> <span data-ttu-id="5b03c-156">Der Schlüssel des gruppierten Indexes ist automatisch in allen nicht gruppierten Indizes enthalten, wozu auch gefilterte Indizes zählen.</span><span class="sxs-lookup"><span data-stu-id="5b03c-156">The clustered index key is automatically included in all nonclustered indexes, including filtered indexes.</span></span>  
  
-   <span data-ttu-id="5b03c-157">Wenn der im gefilterten Indexausdruck der gefilterten Indexergebnisse angegebene Vergleichsoperator eine implizite oder explizite Datenkonvertierung ergibt, kommt es zu einem Fehler, wenn die Konvertierung auf der linken Seite eines Vergleichsoperators auftritt.</span><span class="sxs-lookup"><span data-stu-id="5b03c-157">If the comparison operator specified in the filtered index expression of the filtered index results in an implicit or explicit data conversion, an error will occur if the conversion occurs on the left side of a comparison operator.</span></span> <span data-ttu-id="5b03c-158">Eine mögliche Lösung besteht darin, den gefilterten Indexausdruck mit dem Datenkonvertierungsoperator (CAST oder CONVERT) auf die rechte Seite des Vergleichsoperators zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="5b03c-158">A solution is to write the filtered index expression with the data conversion operator (CAST or CONVERT) on the right side of the comparison operator.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5b03c-159">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5b03c-159">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5b03c-160">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5b03c-160">Permissions</span></span>  
 <span data-ttu-id="5b03c-161">Erfordert die ALTER-Berechtigung in der Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="5b03c-161">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="5b03c-162">Der Benutzer muss ein Mitglied der festen Serverrolle **sysadmin** bzw. der festen Datenbankrollen **db_ddladmin** und **db_owner** sein.</span><span class="sxs-lookup"><span data-stu-id="5b03c-162">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span> <span data-ttu-id="5b03c-163">Verwenden Sie CREATE INDEX WITH DROP_EXISTING, um den gefilterten Indexausdruck zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5b03c-163">To modify the filtered index expression, use CREATE INDEX WITH DROP_EXISTING.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5b03c-164">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b03c-164">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-filtered-index"></a><span data-ttu-id="5b03c-165">So erstellen Sie einen gefilterten Index</span><span class="sxs-lookup"><span data-stu-id="5b03c-165">To create a filtered index</span></span>  
  
1.  <span data-ttu-id="5b03c-166">Klicken Sie in Objekt-Explorer auf das Pluszeichen, um die Datenbank zu erweitern, die die Tabelle enthält, in der Sie einen gefilterten Index erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="5b03c-166">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to create a filtered index.</span></span>  
  
2.  <span data-ttu-id="5b03c-167">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="5b03c-167">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="5b03c-168">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, in der Sie einen gefilterten Index erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="5b03c-168">Click the plus sign to expand the table on which you want to create a filtered index.</span></span>  
  
4.  <span data-ttu-id="5b03c-169">Klicken Sie mit der rechten Maustaste auf den Ordner **Indizes**, zeigen Sie auf **Neuer Index**, und wählen Sie **Nicht gruppierter Index...** aus.</span><span class="sxs-lookup"><span data-stu-id="5b03c-169">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="5b03c-170">Geben Sie in das Dialogfeld **Neuer Index** auf der Seite **Allgemein** den Namen des neuen Indexes in das Feld **Indexname** ein.</span><span class="sxs-lookup"><span data-stu-id="5b03c-170">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="5b03c-171">Klicken Sie unter **Indexschlüsselspalten** auf **Hinzufügen…** .</span><span class="sxs-lookup"><span data-stu-id="5b03c-171">Under **Index key columns**, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="5b03c-172">Aktivieren Sie im Dialogfeld **Spalten auswählen aus**_table_name_ das Kontrollkästchen bzw. die Kontrollkästchen der Tabellenspalte oder der Spalten, die dem eindeutigen Index hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5b03c-172">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the unique index.</span></span>  
  
8.  <span data-ttu-id="5b03c-173">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b03c-173">Click **OK**.</span></span>  
  
9. <span data-ttu-id="5b03c-174">Geben Sie auf der Seite **Filter** unter **Filterausdruck** den SQL-Ausdruck ein, mit dem Sie den gefilterten Index erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b03c-174">On the **Filter** page, under **Filter Expression**, enter SQL expression that you'll use to create the filtered index.</span></span>  
  
10. <span data-ttu-id="5b03c-175">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b03c-175">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5b03c-176">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b03c-176">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-filtered-index"></a><span data-ttu-id="5b03c-177">So erstellen Sie einen gefilterten Index</span><span class="sxs-lookup"><span data-stu-id="5b03c-177">To create a filtered index</span></span>  
  
1.  <span data-ttu-id="5b03c-178">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="5b03c-178">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5b03c-179">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="5b03c-179">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5b03c-180">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5b03c-180">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Looks for an existing filtered index named "FIBillOfMaterialsWithEndDate"  
    -- and deletes it from the table Production.BillOfMaterials if found.   
    IF EXISTS (SELECT name FROM sys.indexes  
        WHERE name = N'FIBillOfMaterialsWithEndDate'  
        AND object_id = OBJECT_ID (N'Production.BillOfMaterials'))  
    DROP INDEX FIBillOfMaterialsWithEndDate  
        ON Production.BillOfMaterials  
    GO  
    -- Creates a filtered index "FIBillOfMaterialsWithEndDate"  
    -- on the table Production.BillOfMaterials   
    -- using the columms ComponentID and StartDate.  
  
    CREATE NONCLUSTERED INDEX FIBillOfMaterialsWithEndDate  
        ON Production.BillOfMaterials (ComponentID, StartDate)  
        WHERE EndDate IS NOT NULL ;  
    GO  
    ```  
  
     <span data-ttu-id="5b03c-181">Der obenstehende gefilterte Index ist für die folgende Abfrage gültig.</span><span class="sxs-lookup"><span data-stu-id="5b03c-181">The filtered index above is valid for the following query.</span></span> <span data-ttu-id="5b03c-182">Sie können den Abfrageausführungsplan anzeigen, um zu bestimmen, ob der Abfrageoptimierer den gefilterten Index verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="5b03c-182">You can display the query execution plan to determine if the query optimizer used the filtered index.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT ProductAssemblyID, ComponentID, StartDate   
    FROM Production.BillOfMaterials  
    WHERE EndDate IS NOT NULL   
        AND ComponentID = 5   
        AND StartDate > '01/01/2008' ;  
    GO  
    ```  
  
#### <a name="to-ensure-that-a-filtered-index-is-used-in-a-sql-query"></a><span data-ttu-id="5b03c-183">So stellen Sie sicher, dass ein gefilterter Index in einer SQL-Abfrage verwendet wird</span><span class="sxs-lookup"><span data-stu-id="5b03c-183">To ensure that a filtered index is used in a SQL query</span></span>  
  
1.  <span data-ttu-id="5b03c-184">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="5b03c-184">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5b03c-185">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="5b03c-185">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5b03c-186">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5b03c-186">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT ComponentID, StartDate FROM Production.BillOfMaterials  
        WITH ( INDEX ( FIBillOfMaterialsWithEndDate ) )   
    WHERE EndDate IN ('20000825', '20000908', '20000918');   
    GO  
    ```  
  
 <span data-ttu-id="5b03c-187">Weitere Informationen finden Sie unter [CCREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5b03c-187">For more information, see  [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
