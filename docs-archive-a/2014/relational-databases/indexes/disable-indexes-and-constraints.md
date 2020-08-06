---
title: Deaktivieren von Indizes und Einschränkungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.disableindexes.f1
helpviewer_keywords:
- disabled indexes [SQL Server], index operations
- nonclustered indexes [SQL Server], disabling
- disabled indexes [SQL Server], guidelines
- clustered indexes, disabling
- constraints [SQL Server], disabling
- disabled indexes [SQL Server], viewing
- FOREIGN KEY constraints, disabling
- statistical information [SQL Server], indexes
- index disabling [SQL Server]
- indexed views [SQL Server], disabled indexes
ms.assetid: 2198f1af-fa44-47e9-92df-f4fde322ba18
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 40f9de4108be4defeb2353a9e7835c289641a819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724605"
---
# <a name="disable-indexes-and-constraints"></a><span data-ttu-id="e20ed-102">Deaktivieren von Indizes und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e20ed-102">Disable Indexes and Constraints</span></span>
  <span data-ttu-id="e20ed-103">In diesem Thema wird beschrieben, wie ein Index oder Einschränkungen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e20ed-103">This topic describes how to disable an index or constraints in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e20ed-104">Wenn Indizes deaktiviert werden, können Benutzer nicht mehr darauf zugreifen, und bei gruppierten Indizes können sie auch nicht mehr auf die dem Index zugrunde liegenden Tabellendaten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e20ed-104">Disabling an index prevents user access to the index, and for clustered indexes to the underlying table data.</span></span> <span data-ttu-id="e20ed-105">Die Indexdefinition verbleibt jedoch in den Metadaten, und bei nicht gruppierten Indizes werden die Indexstatistiken beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e20ed-105">The index definition remains in metadata, and index statistics are kept on nonclustered indexes.</span></span> <span data-ttu-id="e20ed-106">Beim Deaktivieren eines nicht gruppierten oder gruppierten Indexes in einer Sicht werden die Indexdaten physisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="e20ed-106">Disabling a nonclustered or clustered index on a view physically deletes the index data.</span></span> <span data-ttu-id="e20ed-107">Das Deaktivieren eines gruppierten Indexes für eine Tabelle verhindert lediglich das Zugreifen auf die Daten; diese verbleiben in der Tabelle, sind jedoch erst für DML-Vorgänge (Datenbearbeitungssprache) verfügbar, wenn der Index gelöscht oder neu erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e20ed-107">Disabling a clustered index on a table prevents access to the data; the data still remains in the table, but is unavailable for data manipulation language (DML) operations until the index is dropped or rebuilt.</span></span>  
  
 <span data-ttu-id="e20ed-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e20ed-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e20ed-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e20ed-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e20ed-110">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e20ed-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e20ed-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e20ed-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e20ed-112">**So deaktivieren Sie einen Index mithilfe von:**</span><span class="sxs-lookup"><span data-stu-id="e20ed-112">**To disable an index, using:**</span></span>  
  
     [<span data-ttu-id="e20ed-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e20ed-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e20ed-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e20ed-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e20ed-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e20ed-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e20ed-116">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e20ed-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e20ed-117">Der Index wird nicht beibehalten, während er deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e20ed-117">The index is not maintained while it is disabled.</span></span>  
  
-   <span data-ttu-id="e20ed-118">Der deaktivierte Index wird beim Erstellen von Abfrageausführungsplänen nicht vom Abfrageoptimierer berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="e20ed-118">The query optimizer does not consider the disabled index when creating query execution plans.</span></span> <span data-ttu-id="e20ed-119">Des weiteren erzeugen Abfragen einen Fehler, die über einen Tabellenhinweis auf den deaktivierten Index verweisen.</span><span class="sxs-lookup"><span data-stu-id="e20ed-119">Also, queries that reference the disabled index with a table hint fail.</span></span>  
  
-   <span data-ttu-id="e20ed-120">Sie können keinen Index mit dem gleichen Namen erstellen, den ein vorhandener deaktivierter Index aufweist.</span><span class="sxs-lookup"><span data-stu-id="e20ed-120">You cannot create an index that uses the same name as an existing disabled index.</span></span>  
  
-   <span data-ttu-id="e20ed-121">Ein deaktivierter Index kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e20ed-121">A disabled index can be dropped.</span></span>  
  
-   <span data-ttu-id="e20ed-122">Beim Deaktivieren eines eindeutigen Indexes werden die PRIMARY KEY- oder UNIQUE-Einschränkung sowie alle FOREIGN KEY-Einschränkungen, die aus anderen Tabellen auf die indizierten Spalten verweisen, ebenfalls deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e20ed-122">When disabling a unique index, the PRIMARY KEY or UNIQUE constraint and all FOREIGN KEY constraints that reference the indexed columns from other tables are also disabled.</span></span> <span data-ttu-id="e20ed-123">Beim Deaktivieren eines gruppierten Indexes werden alle eingehenden und ausgehenden FOREIGN KEY-Einschränkungen der zugrunde liegenden Tabelle ebenfalls deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e20ed-123">When disabling a clustered index, all incoming and outgoing FOREIGN KEY constraints on the underlying table are also disabled.</span></span> <span data-ttu-id="e20ed-124">Die Namen der Einschränkungen werden in einer Warnmeldung aufgeführt, wenn der Index deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="e20ed-124">The constraint names are listed in a warning message when the index is disabled.</span></span> <span data-ttu-id="e20ed-125">Nach dem Neuerstellen des Indexes müssen alle Einschränkungen mithilfe der ALTER TABLE CHECK CONSTRAINT-Anweisung manuell aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e20ed-125">After rebuilding the index, all constraints must be manually enabled by using the ALTER TABLE CHECK CONSTRAINT statement.</span></span>  
  
-   <span data-ttu-id="e20ed-126">Nicht gruppierte Indizes werden mit dem Deaktivieren des gruppierten Indexes, dem sie zugeordnet sind, automatisch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e20ed-126">Nonclustered indexes are automatically disabled when the associated clustered index is disabled.</span></span> <span data-ttu-id="e20ed-127">Sie können nicht mehr aktiviert werden, bis der gruppierte Index der Tabelle oder Sicht aktiviert bzw. der gruppierte Index der Tabelle gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="e20ed-127">They cannot be enabled until either the clustered index on the table or view is enabled or the clustered index on the table is dropped.</span></span> <span data-ttu-id="e20ed-128">Nicht gruppierte Indizes müssen explizit aktiviert werden, es sei denn, der gruppierte Index wurde mithilfe der ALTER INDEX ALL REBUILD-Anweisung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e20ed-128">Nonclustered indexes must be explicitly enabled, unless the clustered index was enabled by using the ALTER INDEX ALL REBUILD statement.</span></span>  
  
-   <span data-ttu-id="e20ed-129">Die ALTER INDEX ALL REBUILD-Anweisung erstellt alle deaktivierten Indizes der Tabelle neu und aktiviert sie, mit Ausnahme von deaktivierten Indizes für Sichten.</span><span class="sxs-lookup"><span data-stu-id="e20ed-129">The ALTER INDEX ALL REBUILD statement rebuilds and enables all disabled indexes on the table, except for disabled indexes on views.</span></span> <span data-ttu-id="e20ed-130">Indizes für Sichten müssen durch eine separate ALTER INDEX ALL REBUILD-Anweisung aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e20ed-130">Indexes on views must be enabled in a separate ALTER INDEX ALL REBUILD statement.</span></span>  
  
-   <span data-ttu-id="e20ed-131">Beim Deaktivieren eines gruppierten Indexes auf einer Tabelle werden auch alle gruppierten und nicht gruppierten Indizes in Sichten deaktiviert, die auf diese Tabelle verweisen.</span><span class="sxs-lookup"><span data-stu-id="e20ed-131">Disabling a clustered index on a table also disables all clustered and nonclustered indexes on views that reference that table.</span></span> <span data-ttu-id="e20ed-132">Diese Indizes müssen genau wie die Indizes der Tabelle, auf die sie verweisen, neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e20ed-132">These indexes must be rebuilt just as those on the referenced table.</span></span>  
  
-   <span data-ttu-id="e20ed-133">Auf die Datenzeilen des deaktivierten gruppierten Indexes kann nicht zugegriffen werden, mit Ausnahme von Zugriffen zum Löschen oder Neuerstellen des gruppierten Indexes.</span><span class="sxs-lookup"><span data-stu-id="e20ed-133">The data rows of the disabled clustered index cannot be accessed except to drop or rebuild the clustered index.</span></span>  
  
-   <span data-ttu-id="e20ed-134">Sie können einen deaktivierten nicht gruppierten Index online neu erstellen, wenn die Tabelle über einen gruppierten Index verfügt, der nicht deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e20ed-134">You can rebuild a disabled nonclustered index online when the table does not have a disabled clustered index.</span></span> <span data-ttu-id="e20ed-135">Sie müssen jedoch einen deaktivierten gruppierten Index immer offline neu erstellen, wenn Sie die ALTER INDEX REBUILD- oder CREATE INDEX WITH DROP_EXISTING-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="e20ed-135">However, you must always rebuild a disabled clustered index offline if you use either the ALTER INDEX REBUILD or CREATE INDEX WITH DROP_EXISTING statement.</span></span> <span data-ttu-id="e20ed-136">Weitere Informationen zu Onlineindexvorgängen finden Sie unter [Ausführen von Onlineindexvorgängen](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="e20ed-136">For more information about online index operations, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
-   <span data-ttu-id="e20ed-137">Die CREATE STATISTICS-Anweisung kann nicht für eine Tabelle mit einem deaktivierten gruppierten Index ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e20ed-137">The CREATE STATISTICS statement cannot be successfully executed on a table that has a disabled clustered index.</span></span>  
  
-   <span data-ttu-id="e20ed-138">Die AUTO_CREATE_STATISTICS-Datenbankoption erstellt neue Statistiken für eine Spalte, wenn der Index deaktiviert ist und folgende Bedingungen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="e20ed-138">The AUTO_CREATE_STATISTICS database option creates new statistics on a column when the index is disabled and the following conditions exist:</span></span>  
  
    -   <span data-ttu-id="e20ed-139">AUTO_CREATE_STATISTICS ist auf ON festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e20ed-139">AUTO_CREATE_STATISTICS is set to ON</span></span>  
  
    -   <span data-ttu-id="e20ed-140">Es sind keine Statistiken für die Spalte vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e20ed-140">There are no existing statistics for the column.</span></span>  
  
    -   <span data-ttu-id="e20ed-141">Statistiken sind während der Abfrageoptimierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e20ed-141">Statistics are required during query optimization.</span></span>  
  
-   <span data-ttu-id="e20ed-142">Ist ein gruppierter Index deaktiviert, kann [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) keine Informationen über die zugrunde liegende Tabelle zurückgeben. Stattdessen meldet die Anweisung, dass der gruppierte Index deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e20ed-142">If a clustered index is disabled, [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) cannot return information about the underlying table; instead, the statement reports that the clustered index is disabled.</span></span> <span data-ttu-id="e20ed-143">[DBCC INDEXDEFRAG](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql) kann nicht zur Defragmentierung eines deaktivierten Indexes verwendet werden. Die Anweisung schlägt mit einer Fehlermeldung fehl.</span><span class="sxs-lookup"><span data-stu-id="e20ed-143">[DBCC INDEXDEFRAG](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql) cannot be used to defragment a disabled index; the statement fails with an error message.</span></span> <span data-ttu-id="e20ed-144">Zum Neuerstellen eines deaktivierten Indexes können Sie [DBCC DBREINDEX](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) verwenden.</span><span class="sxs-lookup"><span data-stu-id="e20ed-144">You can use [DBCC DBREINDEX](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) to rebuild a disabled index.</span></span>  
  
-   <span data-ttu-id="e20ed-145">Durch Erstellen eines neuen gruppierten Indexes werden zuvor deaktivierte nicht gruppierte Indizes aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e20ed-145">Creating a new clustered index enables previously disabled nonclustered indexes.</span></span> <span data-ttu-id="e20ed-146">Weitere Informationen finden Sie unter [Enable Indexes and Constraints](enable-indexes-and-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="e20ed-146">For more information, see [Enable Indexes and Constraints](enable-indexes-and-constraints.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e20ed-147">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e20ed-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e20ed-148">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e20ed-148">Permissions</span></span>  
 <span data-ttu-id="e20ed-149">Zum Ausführen von ALTER INDEX benötigen Sie mindestens die ALTER-Berechtigung auf der Tabelle bzw. Sicht.</span><span class="sxs-lookup"><span data-stu-id="e20ed-149">To execute ALTER INDEX, at a minimum, ALTER permission on the table or view is required.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e20ed-150">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e20ed-150">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-an-index"></a><span data-ttu-id="e20ed-151">So deaktivieren Sie einen Index</span><span class="sxs-lookup"><span data-stu-id="e20ed-151">To disable an index</span></span>  
  
1.  <span data-ttu-id="e20ed-152">Klicken Sie in Objekt-Explorer auf das Pluszeichen, um die Datenbank zu erweitern, die die Tabelle enthält, in der Sie einen Index deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e20ed-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to disable an index.</span></span>  
  
2.  <span data-ttu-id="e20ed-153">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e20ed-153">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="e20ed-154">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, in der Sie einen Index deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e20ed-154">Click the plus sign to expand the table on which you want to disable an index.</span></span>  
  
4.  <span data-ttu-id="e20ed-155">Klicken Sie auf das Pluszeichen, um den Ordner **Indizes** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e20ed-155">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="e20ed-156">Klicken Sie mit der rechten Maustaste auf den Index, den Sie deaktivieren möchten, und wählen Sie **Deaktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="e20ed-156">Right-click the index you want to disable and select **Disable**.</span></span>  
  
6.  <span data-ttu-id="e20ed-157">Überprüfen Sie im Dialogfeld **Index deaktivieren** , dass der richtige Index im Raster **Zu deaktivierende Indizes** ausgewählt ist, und klicken sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e20ed-157">In the **Disable Indexes** dialog box, verify that the correct index is in the **Indexes to disable** grid and click **OK**.</span></span>  
  
#### <a name="to-disable-all-indexes-on-a-table"></a><span data-ttu-id="e20ed-158">So deaktivieren Sie alle Indizes in einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="e20ed-158">To disable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="e20ed-159">Klicken Sie in Objekt-Explorer auf das Pluszeichen, um die Datenbank zu erweitern, die die Tabelle enthält, in der Sie die Indizes deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e20ed-159">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to disable the indexes.</span></span>  
  
2.  <span data-ttu-id="e20ed-160">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e20ed-160">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="e20ed-161">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, in der Sie die Indizes deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e20ed-161">Click the plus sign to expand the table on which you want to disable the indexes.</span></span>  
  
4.  <span data-ttu-id="e20ed-162">Klicken Sie mit der rechten Maustaste auf den Ordner **Indizes** , und wählen Sie **Alle deaktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="e20ed-162">Right-click the **Indexes** folder and select **Disable All**.</span></span>  
  
5.  <span data-ttu-id="e20ed-163">Überprüfen Sie im Dialogfeld **Indizes deaktivieren** , dass die richtigen Indizes im Raster **Zu deaktivierende Indizes** ausgewählt sind, und klicken sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e20ed-163">In the **Disable Indexes** dialog box, verify that the correct indexes are in the **Indexes to disable** grid and click **OK**.</span></span> <span data-ttu-id="e20ed-164">Um einen Index aus dem Raster **Zu deaktivierende Indizes** zu entfernen, wählen Sie den Index aus, und drücken Sie die ENTF-Taste.</span><span class="sxs-lookup"><span data-stu-id="e20ed-164">To remove an index from the **Indexes to disable** grid, select the index and then press the Delete key.</span></span>  
  
 <span data-ttu-id="e20ed-165">Die folgenden Informationen sind im Dialogfeld **Index deaktivieren** verfügbar:</span><span class="sxs-lookup"><span data-stu-id="e20ed-165">The following information is available in the **Disable Indexes** dialog box:</span></span>  
  
 <span data-ttu-id="e20ed-166">**Indexname**</span><span class="sxs-lookup"><span data-stu-id="e20ed-166">**Index Name**</span></span>  
 <span data-ttu-id="e20ed-167">Zeigt den Namen des Indexes an.</span><span class="sxs-lookup"><span data-stu-id="e20ed-167">Displays the name of the index.</span></span> <span data-ttu-id="e20ed-168">Während der Ausführung wird in dieser Spalte auch ein Symbol angezeigt, das den Status wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="e20ed-168">During execution, this column also displays an icon representing the status.</span></span>  
  
 <span data-ttu-id="e20ed-169">**Tabellenname**</span><span class="sxs-lookup"><span data-stu-id="e20ed-169">**Table Name**</span></span>  
 <span data-ttu-id="e20ed-170">Zeigt den Namen der Tabelle oder Sicht an, für die der Index erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e20ed-170">Displays the name of the table or view that the index was created on.</span></span>  
  
 <span data-ttu-id="e20ed-171">**Indextyp**</span><span class="sxs-lookup"><span data-stu-id="e20ed-171">**Index Type**</span></span>  
 <span data-ttu-id="e20ed-172">Zeigt den Typ des Indexes an: **Gruppiert**, **Nicht gruppiert**, **Räumlich**oder **XML**.</span><span class="sxs-lookup"><span data-stu-id="e20ed-172">Displays the type of the index: **Clustered**, **Nonclustered**, **Spatial**, or **XML**.</span></span>  
  
 <span data-ttu-id="e20ed-173">**Status**</span><span class="sxs-lookup"><span data-stu-id="e20ed-173">**Status**</span></span>  
 <span data-ttu-id="e20ed-174">Zeigt den Status des Deaktivierungsvorgangs an.</span><span class="sxs-lookup"><span data-stu-id="e20ed-174">Displays the status of the disable operation.</span></span> <span data-ttu-id="e20ed-175">Mögliche Werte nach der Ausführung:</span><span class="sxs-lookup"><span data-stu-id="e20ed-175">Possible values after execution are:</span></span>  
  
-   <span data-ttu-id="e20ed-176">Leer</span><span class="sxs-lookup"><span data-stu-id="e20ed-176">Blank</span></span>  
  
     <span data-ttu-id="e20ed-177">Vor der Ausführung ist **Status** leer.</span><span class="sxs-lookup"><span data-stu-id="e20ed-177">Prior to execution **Status** is blank.</span></span>  
  
-   <span data-ttu-id="e20ed-178">**Vorgang wird ausgeführt**</span><span class="sxs-lookup"><span data-stu-id="e20ed-178">**In progress**</span></span>  
  
     <span data-ttu-id="e20ed-179">Die Deaktivierung der Indizes wurde gestartet, ist aber noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e20ed-179">Disabling of the indexes has been started but is not complete.</span></span>  
  
-   <span data-ttu-id="e20ed-180">**Erfolgreich**</span><span class="sxs-lookup"><span data-stu-id="e20ed-180">**Success**</span></span>  
  
     <span data-ttu-id="e20ed-181">Der Deaktivierungsvorgang ist erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e20ed-181">The disable operation completed successfully.</span></span>  
  
-   <span data-ttu-id="e20ed-182">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="e20ed-182">**Error**</span></span>  
  
     <span data-ttu-id="e20ed-183">Während des Indexdeaktivierungsvorgangs ist ein Fehler aufgetreten, und der Vorgang wurde nicht erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e20ed-183">An error was encountered during the index disable operation, and the operation did not complete successfully.</span></span>  
  
-   <span data-ttu-id="e20ed-184">**Beendet**</span><span class="sxs-lookup"><span data-stu-id="e20ed-184">**Stopped**</span></span>  
  
     <span data-ttu-id="e20ed-185">Die Deaktivierung des Indexes wurde nicht erfolgreich abgeschlossen, weil der Benutzer den Vorgang gestoppt hat.</span><span class="sxs-lookup"><span data-stu-id="e20ed-185">The disable of the index was not completed successfully because the user stopped the operation.</span></span>  
  
 <span data-ttu-id="e20ed-186">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="e20ed-186">**Message**</span></span>  
 <span data-ttu-id="e20ed-187">Stellt den Text der Fehlermeldungen während des Deaktivierungsvorgangs bereit.</span><span class="sxs-lookup"><span data-stu-id="e20ed-187">Provides the text of error messages during the disable operation.</span></span> <span data-ttu-id="e20ed-188">Während der Ausführung werden die Fehler als Links angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e20ed-188">During execution, errors appear as hyperlinks.</span></span> <span data-ttu-id="e20ed-189">Der Text der Links beschreibt den Hauptteil des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="e20ed-189">The text of the hyperlinks describes the body of the error.</span></span> <span data-ttu-id="e20ed-190">Die Spalte **Meldung** ist meist nicht breit genug, um den vollständigen Meldungstext lesen zu können.</span><span class="sxs-lookup"><span data-stu-id="e20ed-190">The **Message** column is rarely wide enough to read the full message text.</span></span> <span data-ttu-id="e20ed-191">Der vollständige Text kann auf zwei Arten abgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="e20ed-191">There are two ways to get the full text:</span></span>  
  
-   <span data-ttu-id="e20ed-192">Bewegen Sie den Mauszeiger über die Meldungszelle, um eine QuickInfo mit dem Fehlertext anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e20ed-192">Move the mouse pointer over the message cell to display a ToolTip with the error text.</span></span>  
  
-   <span data-ttu-id="e20ed-193">Klicken Sie auf den Link, um ein Dialogfeld mit dem vollständigen Fehler anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e20ed-193">Click the hyperlink to display a dialog box displaying the full error.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e20ed-194">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e20ed-194">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-an-index"></a><span data-ttu-id="e20ed-195">So deaktivieren Sie einen Index</span><span class="sxs-lookup"><span data-stu-id="e20ed-195">To disable an index</span></span>  
  
1.  <span data-ttu-id="e20ed-196">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="e20ed-196">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e20ed-197">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e20ed-197">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e20ed-198">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e20ed-198">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- disables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    DISABLE;  
    ```  
  
#### <a name="to-disable-all-indexes-on-a-table"></a><span data-ttu-id="e20ed-199">So deaktivieren Sie alle Indizes in einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="e20ed-199">To disable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="e20ed-200">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="e20ed-200">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e20ed-201">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e20ed-201">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e20ed-202">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e20ed-202">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Disables all indexes on the HumanResources.Employee table.  
    ALTER INDEX ALL ON HumanResources.Employee  
    DISABLE;  
    ```  
  
 <span data-ttu-id="e20ed-203">Weitere Informationen finden Sie unter [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e20ed-203">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
