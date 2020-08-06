---
title: Erstellen partitionierter Tabellen und Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.createpartition.partitionscheme.f1
- sql12.swb.createpartition.selectoutput.f1
- sql12.swb.createpartition.finish.f1
- sql12.swb.createpartition.summary.f1
- sql12.swb.createpartition.mappartition.f1
- sql12.swb.createpartition.partitioncolumn.f1
- sql12.swb.createpartition.progress.f1
- sql12.swb.createpartition.createjob.f1
- sql12.swb.createpartition.getstart.f1
- sql12.swb.createpartition.partitionfunction.f1
helpviewer_keywords:
- partitioned indexes [SQL Server], creating
- partition schemes [SQL Server], creating
- partition functions [SQL Server], creating
- partitioned tables [SQL Server], creating
- partition functions [SQL Server]
- partition schemes [SQL Server]
ms.assetid: 7641df10-1921-42a7-ba6e-4cb03b3ba9c8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 76ccd8b784902f8542f06f3823e5f8dcb78e9201
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616507"
---
# <a name="create-partitioned-tables-and-indexes"></a><span data-ttu-id="def17-102">Erstellen partitionierter Tabellen und Indizes</span><span class="sxs-lookup"><span data-stu-id="def17-102">Create Partitioned Tables and Indexes</span></span>
  <span data-ttu-id="def17-103">Sie können in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]eine partitionierte Tabelle oder einen Index erstellen.</span><span class="sxs-lookup"><span data-stu-id="def17-103">You can create a partitioned table or index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="def17-104">Die Daten in partitionierten Tabellen und Indizes werden horizontal in Einheiten aufgeteilt, die über mehrere Dateigruppen in einer Datenbank verteilt werden können.</span><span class="sxs-lookup"><span data-stu-id="def17-104">The data in partitioned tables and indexes is horizontally divided into units that can be spread across more than one filegroup in a database.</span></span> <span data-ttu-id="def17-105">Die Partitionierung kann bewirken, dass sich große Tabellen und Indizes besser verwalten und skalieren lassen.</span><span class="sxs-lookup"><span data-stu-id="def17-105">Partitioning can make large tables and indexes more manageable and scalable.</span></span>  
  
 <span data-ttu-id="def17-106">Das Erstellen einer partitionierten Tabelle oder eines Indexes erfolgt in der Regel in vier Teilen:</span><span class="sxs-lookup"><span data-stu-id="def17-106">Creating a partitioned table or index typically happens in four parts:</span></span>  
  
1.  <span data-ttu-id="def17-107">Erstellen Sie eine Dateigruppe oder Dateigruppen und entsprechende Dateien, die die vom Partitionsschema angegebenen Partitionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="def17-107">Create a filegroup or filegroups and corresponding files that will hold the partitions specified by the partition scheme.</span></span>  
  
2.  <span data-ttu-id="def17-108">Erstellen Sie eine Partitionsfunktion, die die Zeilen einer Tabelle oder eines Indexes Partitionen zuordnet. Dies erfolgt auf Grundlage der Werte einer angegebenen Spalte.</span><span class="sxs-lookup"><span data-stu-id="def17-108">Create a partition function that maps the rows of a table or index into partitions based on the values of a specified column.</span></span>  
  
3.  <span data-ttu-id="def17-109">Erstellen Sie ein Partitionsschema, das die Partitionen einer partitionierten Tabelle oder eines partitionierten Indexes den neuen Dateigruppen zuordnet.</span><span class="sxs-lookup"><span data-stu-id="def17-109">Create a partition scheme that maps the partitions of a partitioned table or index to the new filegroups.</span></span>  
  
4.  <span data-ttu-id="def17-110">Erstellen oder ändern Sie eine Tabelle oder einen Index, und geben Sie das Partitionsschema als Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="def17-110">Create or modify a table or index and specify the partition scheme as the storage location.</span></span>  
  
 <span data-ttu-id="def17-111">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="def17-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="def17-112">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="def17-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="def17-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="def17-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="def17-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="def17-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="def17-115">**Erstellen einer partitionierten Tabelle oder eines partitionierten Indexes mit:**</span><span class="sxs-lookup"><span data-stu-id="def17-115">**To create a partitioned table or index, using:**</span></span>  
  
     [<span data-ttu-id="def17-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="def17-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="def17-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="def17-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="def17-118">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="def17-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="def17-119">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="def17-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="def17-120">Der Bereich einer Partitionsfunktion und eines Schemas ist auf die Datenbank beschränkt, in der er erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="def17-120">The scope of a partition function and scheme is limited to the database in which they have been created.</span></span> <span data-ttu-id="def17-121">Innerhalb der Datenbank befinden sich Partitionsfunktionen in einem von anderen Funktionen abgetrennten Namespace.</span><span class="sxs-lookup"><span data-stu-id="def17-121">Within the database, partition functions reside in a separate namespace from other functions.</span></span>  
  
-   <span data-ttu-id="def17-122">Wenn beliebige Zeilen innerhalb einer Partitionsfunktion Partitionierungsspalten mit NULL-Werten aufweisen, werden diese Zeilen der am weitesten links stehenden Partition zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="def17-122">If any rows within a partition function have partitioning columns with null values, these rows are allocated to the left-most partition.</span></span> <span data-ttu-id="def17-123">Jedoch wenn NULL als Begrenzungswert sowie RIGHT angegeben werden, bleibt die am weitesten links stehende Partition leer, und die NULL-Werte werden in der zweiten Partition eingefügt.</span><span class="sxs-lookup"><span data-stu-id="def17-123">However, if NULL is specified as a boundary value and RIGHT is indicated, the left-most partition remains empty and NULL values are placed in the second partition.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="def17-124">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="def17-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="def17-125">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="def17-125">Permissions</span></span>  
 <span data-ttu-id="def17-126">Zum Erstellen einer partitionierten Tabelle sind die CREATE TABLE-Berechtigung für die Datenbank und die ALTER-Berechtigung für das Schema erforderlich, in dem die Tabelle erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="def17-126">Creating a partitioned table requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span> <span data-ttu-id="def17-127">Das Erstellen eines partitionierten Indexes erfordert die ALTER-Berechtigung für die Tabelle oder Sicht, in der der Index erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="def17-127">Creating a partitioned index requires ALTER permission on the table or view where the index is being created.</span></span> <span data-ttu-id="def17-128">Das Erstellen einer partitionierten Tabelle oder eines partitionierten Indexes erfordert eine der folgenden zusätzlichen Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="def17-128">Creating either a partitioned table or index requires any one of the following additional permissions:</span></span>  
  
-   <span data-ttu-id="def17-129">ALTER ANY DATASPACE-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="def17-129">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="def17-130">Diese Berechtigung gilt standardmäßig für Mitglieder der festen Serverrolle **sysadmin** und für Mitglieder der festen Datenbankrollen **db_owner** und **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="def17-130">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="def17-131">CONTROL- oder ALTER-Berechtigung für die Datenbank, in der die Partitionsfunktion und das Partitionsschema erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="def17-131">CONTROL or ALTER permission on the database in which the partition function and partition scheme are being created.</span></span>  
  
-   <span data-ttu-id="def17-132">CONTROL SERVER- oder ALTER ANY DATABASE-Berechtigung für den Server der Datenbank, in der die Partitionsfunktion und das Partitionsschema erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="def17-132">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition function and partition scheme are being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="def17-133">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="def17-133">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="def17-134">Führen Sie die Schritte in dieser Prozedur aus, um mindestens eine Dateigruppe, entsprechende Dateien und eine Tabelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="def17-134">Follow the steps in this procedure to create one or more filegroups, corresponding files, and a table.</span></span> <span data-ttu-id="def17-135">Sie versehen diese Objekte in der nächsten Prozedur mit Verweisen, wenn Sie die partitionierte Tabelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="def17-135">You will reference these objects in the next procedure when you create the partitioned table.</span></span>  
  
#### <a name="to-create-new-filegroups-for-a-partitioned-table"></a><span data-ttu-id="def17-136">So erstellen Sie neue Dateigruppen für eine partitionierte Tabelle</span><span class="sxs-lookup"><span data-stu-id="def17-136">To create new filegroups for a partitioned table</span></span>  
  
1.  <span data-ttu-id="def17-137">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf die Datenbank, in der Sie eine partitionierte Tabelle erstellen möchten und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="def17-137">In Object Explorer, right-click the database in which you want to create a partitioned table and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="def17-138">Klicken Sie im Dialogfeld **Datenbankeigenschaften -** *database_name* unter **Seite auswählen** auf die Option **Dateigruppen**.</span><span class="sxs-lookup"><span data-stu-id="def17-138">In the **Database Properties -** *database_name* dialog box, under **Select a page**, select **Filegroups**.</span></span>  
  
3.  <span data-ttu-id="def17-139">Klicken Sie unter **Zeilen**auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="def17-139">Under **Rows**, click **Add**.</span></span> <span data-ttu-id="def17-140">Geben Sie in der neuen Zeile den Dateigruppennamen ein.</span><span class="sxs-lookup"><span data-stu-id="def17-140">In the new row, enter the filegroup name.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="def17-141">Zusätzlich zu der Anzahl der für die Begrenzungswerte angegebenen Dateigruppen müssen Sie beim Erstellen von Partitionen stets über eine weitere Dateigruppe verfügen.</span><span class="sxs-lookup"><span data-stu-id="def17-141">You must always have one extra filegroup in addition to the number of filegroups specified for the boundary values when you are creating partitions.</span></span>  
  
4.  <span data-ttu-id="def17-142">Fügen Sie weiterhin Zeilen hinzu, bis Sie alle Dateigruppen für die partitionierte Tabelle erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="def17-142">Continue adding rows until you have created all of the filegroups for the partitioned table.</span></span>  
  
5.  <span data-ttu-id="def17-143">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="def17-143">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="def17-144">Wählen Sie unter **Seite auswählen**die Option **Dateien**aus.</span><span class="sxs-lookup"><span data-stu-id="def17-144">Under **Select a page**, select **Files**.</span></span>  
  
7.  <span data-ttu-id="def17-145">Klicken Sie unter **Zeilen**auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="def17-145">Under **Rows**, click **Add**.</span></span> <span data-ttu-id="def17-146">Geben Sie in der neuen Zeile einen Dateinamen ein, und wählen Sie eine Dateigruppe aus.</span><span class="sxs-lookup"><span data-stu-id="def17-146">In the new row, enter a filename and select a filegroup.</span></span>  
  
8.  <span data-ttu-id="def17-147">Fügen Sie weiter Zeilen hinzu, bis Sie mindestens eine Datei für jede Dateigruppe erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="def17-147">Continue adding rows until you have created at least one file for each filegroup.</span></span>  
  
9. <span data-ttu-id="def17-148">Erweitern Sie den Ordner **Tabellen** , und erstellen Sie eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="def17-148">Expand the **Tables** folder and create a table as you normally would.</span></span> <span data-ttu-id="def17-149">Weitere Informationen finden Sie unter [Verbindungsserver &#40;Datenbank-Engine&#41;](../tables/create-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="def17-149">For more information, see [Create Tables &#40;Database Engine&#41;](../tables/create-tables-database-engine.md).</span></span> <span data-ttu-id="def17-150">Alternativ können Sie in der nächsten Prozedur eine vorhandene Tabelle angeben.</span><span class="sxs-lookup"><span data-stu-id="def17-150">Alternatively, you can specify an existing table in the next procedure.</span></span>  
  
#### <a name="to-create-a-partitioned-table"></a><span data-ttu-id="def17-151">So erstellen Sie eine partitionierte Tabelle</span><span class="sxs-lookup"><span data-stu-id="def17-151">To create a partitioned table</span></span>  
  
1.  <span data-ttu-id="def17-152">Klicken Sie mit der rechten Maustaste auf die Tabelle, die Sie partitionieren möchten, zeigen Sie auf **Speicher**, und klicken Sie dann auf **Partition erstellen...** .</span><span class="sxs-lookup"><span data-stu-id="def17-152">Right-click the table that you wish to partition, point to **Storage**, and then click **Create Partition...**.</span></span>  
  
2.  <span data-ttu-id="def17-153">Klicken Sie im **Assistent zum Erstellen von Partitionen**auf der Seite **Willkommen beim Assistenten zum Erstellen von Partitionen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="def17-153">In the **Create Partition Wizard**, on the **Welcome to the Create Partition Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="def17-154">Wählen Sie auf der Seite **Partitionierungsspalte auswählen** im Raster **Verfügbare Partitionierungsspalten** die Spalte aus, an der Sie die Tabelle partitionieren möchten.</span><span class="sxs-lookup"><span data-stu-id="def17-154">On the **Select a Partitioning Column** page, in the **Available partitioning columns** grid, select the column on which you want to partition your table.</span></span> <span data-ttu-id="def17-155">Im Raster **Verfügbare Partitionierungsspalten** werden nur Spalten mit Datentypen angezeigt, die zum Partitionieren von Daten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="def17-155">Only columns with data types that can be used to partition data will be displayed in the **Available partitioning columns** grid.</span></span> <span data-ttu-id="def17-156">Wenn Sie eine berechnete Spalte als Partitionierungsspalte auswählen, muss die Spalte als persistente berechnete Spalte gekennzeichnet sein.</span><span class="sxs-lookup"><span data-stu-id="def17-156">If you select a computed column as the partitioning column, the column must be designated as a persisted column.</span></span>  
  
     <span data-ttu-id="def17-157">Die Auswahlmöglichkeiten, die Ihnen für die Partitionierungsspalte und den Wertebereich zur Verfügung stehen, werden in erster Linie durch das Ausmaß bestimmt, in dem Ihre Daten auf logische Weise gruppiert werden können.</span><span class="sxs-lookup"><span data-stu-id="def17-157">The choices you have for the partitioning column and the values range are determined primarily by the extent to which your data can be grouped in a logical way.</span></span> <span data-ttu-id="def17-158">So können Sie z. B. die Daten nach Monaten oder Quartalen in logische Gruppierungen aufteilen.</span><span class="sxs-lookup"><span data-stu-id="def17-158">For example, you may choose to divide your data into logical groupings by months or quarters of a year.</span></span> <span data-ttu-id="def17-159">Ob die logische Gruppierung für die Verwaltung der Tabellenpartitionen geeignet ist, hängt von den Abfragen ab, die Sie für die Daten ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="def17-159">The queries you plan to make against your data will determine whether this logical grouping is adequate for managing your table partitions.</span></span> <span data-ttu-id="def17-160">Alle Datentypen sind für die Verwendung als Partitionierungsspalten gültig, außer `text`, `ntext`, `image`, `xml`, `timestamp`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, Aliasdatentypen oder benutzerdefinierte CLR-Datentypen.</span><span class="sxs-lookup"><span data-stu-id="def17-160">All data types are valid for use as partitioning columns, except `text`, `ntext`, `image`, `xml`, `timestamp`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, alias data types, or CLR user-defined data types.</span></span>  
  
     <span data-ttu-id="def17-161">Die folgenden zusätzlichen Optionen sind auf dieser Seite verfügbar:</span><span class="sxs-lookup"><span data-stu-id="def17-161">The following additional options are available on this page:</span></span>  
  
     <span data-ttu-id="def17-162">**Diese Tabelle der ausgewählten partitionierten Tabelle zuordnen**</span><span class="sxs-lookup"><span data-stu-id="def17-162">**Collocate this table to the selected partitioned table**</span></span>  
     <span data-ttu-id="def17-163">Ermöglicht das Auswählen einer partitionierten Tabelle mit verwandten Daten, die über die Partitionierungsspalte mit einer anderen Tabelle verknüpft werden soll.</span><span class="sxs-lookup"><span data-stu-id="def17-163">Allows you to select a partitioned table that contains related data to join with this table on the partitioning column.</span></span> <span data-ttu-id="def17-164">Tabellen mit Partitionen, die über die Partitionierungsspalten verknüpft sind, können i. d. R. effizienter abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="def17-164">Tables with partitions joined on the partitioning columns are typically queried more efficiently.</span></span>  
  
     <span data-ttu-id="def17-165">**Nicht eindeutige Indizes und eindeutige Indizes mit indizierter Partitionsspalte am Speicher ausrichten**</span><span class="sxs-lookup"><span data-stu-id="def17-165">**Storage-align non-unique indexes and unique indexes with an indexed partition column**</span></span>  
     <span data-ttu-id="def17-166">Richtet alle Indizes der Tabelle, die mit dem gleichen Partitionsschema partitioniert sind, aneinander aus.</span><span class="sxs-lookup"><span data-stu-id="def17-166">Aligns all indexes of the table that are partitioned with the same partition scheme.</span></span> <span data-ttu-id="def17-167">Wenn eine Tabelle und ihre Indizes aneinander ausgerichtet sind, können Sie Partitionen effektiver in und aus partitionierten Tabellen verschieben, da die Daten mit dem gleichen Algorithmus partitioniert sind.</span><span class="sxs-lookup"><span data-stu-id="def17-167">When a table and its indexes are aligned, you can move partitions in and out of partitioned tables more effectively, because your data is partitioned with the same algorithm.</span></span>  
  
     <span data-ttu-id="def17-168">Nach der Auswahl der Partitionierungsspalte und beliebiger anderer Optionen klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="def17-168">After selecting the partitioning column and any other options, click **Next**.</span></span>  
  
4.  <span data-ttu-id="def17-169">Klicken Sie auf der Seite **Partitionsfunktion auswählen** unter **Partitionsfunktion auswählen**auf **Neue Partitionsfunktion** oder **Vorhandene Partitionsfunktion**.</span><span class="sxs-lookup"><span data-stu-id="def17-169">On the **Select a Partition Function** page, under **Select partition function**, click either **New partition function** or **Existing partition function**.</span></span> <span data-ttu-id="def17-170">Wenn Sie **Neue Partitionsfunktion**auswählen, geben Sie den Namen der Funktion ein.</span><span class="sxs-lookup"><span data-stu-id="def17-170">If you choose **New partition function**, enter the name of the function.</span></span> <span data-ttu-id="def17-171">Wenn Sie **Vorhandene Partitionsfunktion**auswählen, wählen Sie in der Liste den Namen der Funktion aus, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="def17-171">If you choose **Existing partition function**, select the name of the function you'd like to use from the list.</span></span> <span data-ttu-id="def17-172">Die Option **Vorhandene Partitionsfunktion** ist nicht verfügbar, wenn die Datenbank keine anderen Partitionsfunktionen enthält.</span><span class="sxs-lookup"><span data-stu-id="def17-172">The **Existing partition function** option will not be available if there are no other partition functions on the database.</span></span>  
  
     <span data-ttu-id="def17-173">Nach Fertigstellen dieser Seite klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="def17-173">After completing this page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="def17-174">Klicken Sie auf der Seite **Partitionsschema auswählen** unter **Partitionsschema auswählen**auf **Neues Partitionsschema** oder **Vorhandenes Partitionsschema**.</span><span class="sxs-lookup"><span data-stu-id="def17-174">On the **Select a Partition Scheme** page, under **Select partition scheme**, click either **New partition scheme** or **Existing partition scheme**.</span></span> <span data-ttu-id="def17-175">Wenn Sie **Neues Partitionsschema**auswählen, geben Sie den Namen des Schemas ein.</span><span class="sxs-lookup"><span data-stu-id="def17-175">If you choose **New partition scheme**, enter the name of the scheme.</span></span> <span data-ttu-id="def17-176">Wenn Sie **Vorhandenes Partitionsschema**auswählen, wählen Sie in der Liste den Namen des Schemas aus, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="def17-176">If you choose **Existing partition scheme**, select the name of the scheme you'd like to use from the list.</span></span> <span data-ttu-id="def17-177">Die Option **Vorhandenes Partitionsschema** ist nicht verfügbar, wenn die Datenbank keine anderen Partitionsschemas enthält.</span><span class="sxs-lookup"><span data-stu-id="def17-177">The **Existing partition scheme** option will not be available if there are no other partition schemes on the database.</span></span>  
  
     <span data-ttu-id="def17-178">Nach Fertigstellen dieser Seite klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="def17-178">After completing this page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="def17-179">Wählen Sie auf der Seite **Partitionen zuordnen** unter **Bereich**entweder **Linke Begrenzung** oder **Rechte Begrenzung** aus, um anzugeben, ob der höchste oder niedrigste umgebende Wert in jeder Dateigruppe enthalten sein soll, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="def17-179">On the **Map Partitions** page, under **Range**, select either **Left boundary** or **Right boundary** to specify whether to include the highest or lowest bounding value within each filegroup you create.</span></span> <span data-ttu-id="def17-180">Zusätzlich zu der Anzahl der für die Begrenzungswerte angegebenen Dateigruppen müssen Sie beim Erstellen von Partitionen stets eine weitere Dateigruppe eingeben.</span><span class="sxs-lookup"><span data-stu-id="def17-180">You must always enter one extra filegroup in addition to the number of filegroups specified for the boundary values when you are creating partitions.</span></span>  
  
     <span data-ttu-id="def17-181">Wählen Sie im Raster **Wählen Sie Dateigruppen aus, und geben Sie Begrenzungswerte an** unter **Dateigruppe**die Dateigruppe aus, in die Sie die Daten partitionieren möchten.</span><span class="sxs-lookup"><span data-stu-id="def17-181">In the **Select filegroups and specify boundary values** grid, under **Filegroup**, select the filegroup into which you want to partition your data.</span></span> <span data-ttu-id="def17-182">Geben Sie unter **Begrenzung**den Begrenzungswert für jede Dateigruppe ein.</span><span class="sxs-lookup"><span data-stu-id="def17-182">Under **Boundary**, enter the boundary value for each filegroup.</span></span> <span data-ttu-id="def17-183">Wenn der Begrenzungswert leer bleibt, ordnet die Partitionsfunktion die gesamte Tabelle oder den gesamten Index mithilfe eines einzigen Partitionsfunktionsnamens zu.</span><span class="sxs-lookup"><span data-stu-id="def17-183">If boundary value is left empty, the partition function maps the whole table or index into a single partition using the partition function name.</span></span>  
  
     <span data-ttu-id="def17-184">Die folgenden zusätzlichen Optionen sind auf dieser Seite verfügbar:</span><span class="sxs-lookup"><span data-stu-id="def17-184">The following additional options are available on this page:</span></span>  
  
     <span data-ttu-id="def17-185">**Begrenzungen festlegen...**</span><span class="sxs-lookup"><span data-stu-id="def17-185">**Set Boundaries...**</span></span>  
     <span data-ttu-id="def17-186">Öffnet das Dialogfeld **Begrenzungswerte festlegen** , um die Begrenzungswerte und Datumsbereiche für die Partitionen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="def17-186">Opens the **Set Boundary Values** dialog box to select the boundary values and date ranges you want for your partitions.</span></span> <span data-ttu-id="def17-187">Diese Option ist nur verfügbar, wenn Sie eine Partitionierungs Spalte ausgewählt haben, die einen der folgenden Datentypen enthält: `date` , `datetime` , `smalldatetime` , `datetime2` oder `datetimeoffset` .</span><span class="sxs-lookup"><span data-stu-id="def17-187">This option is only available when you have selected a partitioning column that contains one of the following data types: `date`, `datetime`, `smalldatetime`, `datetime2`, or `datetimeoffset`.</span></span>  
  
     <span data-ttu-id="def17-188">**Schätzungsspeicher**</span><span class="sxs-lookup"><span data-stu-id="def17-188">**Estimate storage**</span></span>  
     <span data-ttu-id="def17-189">Schätzt die Zeilenanzahl sowie den zum Speichern erforderlichen und verfügbaren Speicherplatz für jede für die Partitionen angegebene Dateigruppe.</span><span class="sxs-lookup"><span data-stu-id="def17-189">Estimates rowcount, required space, and available space for storage for each filegroup specified for the partitions.</span></span> <span data-ttu-id="def17-190">Diese Werte werden im Raster als schreibgeschützte Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="def17-190">These values are displayed in the grid as read-only values.</span></span>  
  
     <span data-ttu-id="def17-191">Das Dialogfeld **Begrenzungswerte festlegen** berücksichtigt die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="def17-191">The **Set Boundary Values** dialog box allows for the following additional options:</span></span>  
  
     <span data-ttu-id="def17-192">**Startdatum**</span><span class="sxs-lookup"><span data-stu-id="def17-192">**Start date**</span></span>  
     <span data-ttu-id="def17-193">Wählt das Anfangsdatum für die Bereichswerte der Partitionen aus.</span><span class="sxs-lookup"><span data-stu-id="def17-193">Selects the starting date for the range values of your partitions.</span></span>  
  
     <span data-ttu-id="def17-194">**Enddatum**</span><span class="sxs-lookup"><span data-stu-id="def17-194">**End date**</span></span>  
     <span data-ttu-id="def17-195">Wählt das Enddatum für die Bereichswerte der Partitionen aus.</span><span class="sxs-lookup"><span data-stu-id="def17-195">Selects the ending date for the range values of your partitions.</span></span> <span data-ttu-id="def17-196">Wenn Sie auf der Seite **Partitionen zuordnen** die Option **Linke Begrenzung** ausgewählt haben, ist dieses Datum der letzte Wert für alle Dateigruppen/Partition.</span><span class="sxs-lookup"><span data-stu-id="def17-196">If you selected **Left boundary** on the **Map Partitions** page, this date will be the last value for each filegroup/partition.</span></span> <span data-ttu-id="def17-197">Wenn Sie auf der Seite **Partitionen zuordnen** die Option **Rechte Begrenzung** wählen, ist dieses Datum der erste Wert in der vorletzten Dateigruppe.</span><span class="sxs-lookup"><span data-stu-id="def17-197">If you selected **Right boundary** on the **Map Partitions** page, this date will be the first value in the next-to-last filegroup.</span></span>  
  
     <span data-ttu-id="def17-198">**Datumsbereich**</span><span class="sxs-lookup"><span data-stu-id="def17-198">**Date range**</span></span>  
     <span data-ttu-id="def17-199">Wählt die Datumsgranularität bzw. das Bereichswertinkrement für jede Partition aus.</span><span class="sxs-lookup"><span data-stu-id="def17-199">Selects the date granularity or range value increment you want for each partition.</span></span>  
  
     <span data-ttu-id="def17-200">Nach Fertigstellen dieser Seite klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="def17-200">After completing this page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="def17-201">Geben Sie auf der Seite **Ausgabeoption auswählen** an, wie Sie die partitionierte Tabelle fertigstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="def17-201">In the **Select an Output Option** page, specify how you want to complete your partitioned table.</span></span> <span data-ttu-id="def17-202">Wählen Sie **Skript erstellen** aus, um ein auf den vorherigen Seiten im Assistenten basierendes SQL-Skript zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="def17-202">Select **Create Script** to create a SQL script based the previous pages in the wizard.</span></span> <span data-ttu-id="def17-203">Wählen Sie **Sofort ausführen** aus, um die neue partitionierte Tabelle zu erstellen, nachdem Sie alle verbleibenden Seiten im Assistenten vervollständigt haben.</span><span class="sxs-lookup"><span data-stu-id="def17-203">Select **Run immediately** to create the new partitioned table after completing all remaining pages in the wizard.</span></span> <span data-ttu-id="def17-204">Wählen Sie **Zeitplan** aus, um die neue partitionierte Tabelle zu einer vorher bestimmten Zeit für die Zukunft zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="def17-204">Select **Schedule** to create the new partitioned table at a predetermined time in the future.</span></span>  
  
     <span data-ttu-id="def17-205">Wenn Sie **Skript erstellen**auswählen, sind die folgenden Optionen unter **Skriptoptionen**verfügbar:</span><span class="sxs-lookup"><span data-stu-id="def17-205">If you select **Create script**, the following options are available under **Script options**:</span></span>  
  
     <span data-ttu-id="def17-206">**Skript in Datei schreiben**</span><span class="sxs-lookup"><span data-stu-id="def17-206">**Script to file**</span></span>  
     <span data-ttu-id="def17-207">Generiert das Skript als SQL-Datei.</span><span class="sxs-lookup"><span data-stu-id="def17-207">Generates the script as a .sql file.</span></span> <span data-ttu-id="def17-208">Geben Sie in das Dialogfeld **Dateiname** einen Dateinamen und einen Speicherort ein, oder klicken Sie auf **Durchsuchen** , um das Dialogfeld **Speicherort der Skriptdatei** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="def17-208">Enter a file name and location in the **File name** box or click **Browse** to open the **Script File Location** dialog box.</span></span> <span data-ttu-id="def17-209">Wählen Sie in **Speichern unter** **Unicode-Text** oder **ANSI-Text**aus.</span><span class="sxs-lookup"><span data-stu-id="def17-209">From **Save As**, select **Unicode text** or **ANSI text**.</span></span>  
  
     <span data-ttu-id="def17-210">**Skript in Zwischenablage schreiben**</span><span class="sxs-lookup"><span data-stu-id="def17-210">**Script to Clipboard**</span></span>  
     <span data-ttu-id="def17-211">Speichert das Skript in der Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="def17-211">Saves the script to the Clipboard.</span></span>  
  
     <span data-ttu-id="def17-212">**Skript in Fenster "Neue Abfrage" schreiben**</span><span class="sxs-lookup"><span data-stu-id="def17-212">**Script to New Query Window**</span></span>  
     <span data-ttu-id="def17-213">Generiert das Skript in einem neuen Abfrage-Editor-Fenster.</span><span class="sxs-lookup"><span data-stu-id="def17-213">Generates the script to a new Query Editor window.</span></span> <span data-ttu-id="def17-214">Dies ist die Standardauswahl.</span><span class="sxs-lookup"><span data-stu-id="def17-214">This is the default selection.</span></span>  
  
     <span data-ttu-id="def17-215">Wenn Sie **Zeitplan**auswählen, klicken Sie auf **Zeitplan ändern**.</span><span class="sxs-lookup"><span data-stu-id="def17-215">If you select **Schedule**, click **Change schedule**.</span></span>  
  
    1.  <span data-ttu-id="def17-216">Geben Sie im Dialogfeld **Neuer Auftragszeitplan** im Feld **Name** den Namen des Auftragszeitplans ein.</span><span class="sxs-lookup"><span data-stu-id="def17-216">In the **New Job Schedule** dialog box, in the **Name** box, enter the job schedule's name.</span></span>  
  
    2.  <span data-ttu-id="def17-217">Wählen Sie in der Liste **Zeitplantyp** den Zeitplantyp aus:</span><span class="sxs-lookup"><span data-stu-id="def17-217">On the **Schedule type** list, select the type of schedule:</span></span>  
  
        -   <span data-ttu-id="def17-218">**Automatisch starten, wenn der SQL Server-Agent startet**</span><span class="sxs-lookup"><span data-stu-id="def17-218">**Start automatically when SQL Server Agent starts**</span></span>  
  
        -   <span data-ttu-id="def17-219">**Starten, wenn sich die CPUs im Leerlauf befinden**</span><span class="sxs-lookup"><span data-stu-id="def17-219">**Start whenever the CPUs become idle**</span></span>  
  
        -   <span data-ttu-id="def17-220">**Wiederholt**.</span><span class="sxs-lookup"><span data-stu-id="def17-220">**Recurring**.</span></span> <span data-ttu-id="def17-221">Aktivieren Sie diese Option, wenn die neue partitionierte Tabellen regelmäßig mit neuen Informationen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="def17-221">Select this option if your new partitioned table updates with new information on a regular basis.</span></span>  
  
        -   <span data-ttu-id="def17-222">**Einmalige Ausführung**.</span><span class="sxs-lookup"><span data-stu-id="def17-222">**One time**.</span></span> <span data-ttu-id="def17-223">Dies ist die Standardauswahl.</span><span class="sxs-lookup"><span data-stu-id="def17-223">This is the default selection.</span></span>  
  
    3.  <span data-ttu-id="def17-224">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Aktiviert** , um den Zeitplan zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="def17-224">Select or clear the **Enabled** check box to enable or disable the schedule.</span></span>  
  
    4.  <span data-ttu-id="def17-225">Wenn Sie **Wiederholt**auswählen:</span><span class="sxs-lookup"><span data-stu-id="def17-225">If you select **Recurring**:</span></span>  
  
        1.  <span data-ttu-id="def17-226">Geben Sie unter **Häufigkeit**in der Liste **Tritt auf** die Häufigkeit des Vorkommens an:</span><span class="sxs-lookup"><span data-stu-id="def17-226">Under **Frequency**, on the **Occurs** list, specify the frequency of occurrence:</span></span>  
  
            -   <span data-ttu-id="def17-227">Wenn Sie im Dialogfeld **Wiederholen alle**die Option **Täglich** auswählen, geben Sie ein, wie oft der Auftragszeitplan wiederholt wird (in Tagen).</span><span class="sxs-lookup"><span data-stu-id="def17-227">If you select **Daily**, in the **Recurs every** box, enter how often the job schedule repeats in days.</span></span>  
  
            -   <span data-ttu-id="def17-228">Wenn Sie im Dialogfeld **Wiederholen alle**die Option **Wöchentlich** auswählen, geben Sie ein, wie oft der Auftragszeitplan wiederholt wird (in Wochen).</span><span class="sxs-lookup"><span data-stu-id="def17-228">If you select **Weekly**, in the **Recurs every** box, enter how often the job schedule repeats in weeks.</span></span> <span data-ttu-id="def17-229">Wählen Sie den Tag oder die Tage der Woche aus, an denen der Auftragszeitplan ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="def17-229">Select the day or days of the week on which the job schedule is run.</span></span>  
  
            -   <span data-ttu-id="def17-230">Wenn Sie **Monatlich**auswählen, wählen Sie **Tag** oder **Am**aus.</span><span class="sxs-lookup"><span data-stu-id="def17-230">If you select **Monthly**, select either **Day** or **The**.</span></span>  
  
                -   <span data-ttu-id="def17-231">Wenn Sie **Tag**auswählen, geben Sie das Datum ein, an dem der Auftragszeitplan ausgeführt wird, und wie oft der Auftragszeitplan wiederholt werden soll (in Monaten).</span><span class="sxs-lookup"><span data-stu-id="def17-231">If you select **Day**, enter both the date of the month you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="def17-232">Wenn Sie beispielsweise möchten, dass der Auftragszeitplan jeden zweiten Monat am 15. ausgeführt wird, wählen Sie **Tag** aus, und geben Sie in das erste Feld „15“ und in das zweite Feld „2“ ein.</span><span class="sxs-lookup"><span data-stu-id="def17-232">For example, if you want the job schedule to run on the 15th day of the month every other month, select **Day** and enter "15" in the first box and "2" in the second box.</span></span> <span data-ttu-id="def17-233">Beachten Sie, dass die größte im zweiten Feld zulässige Zahl „99“ ist.</span><span class="sxs-lookup"><span data-stu-id="def17-233">Please note that the largest number allowed in the second box is "99".</span></span>  
  
                -   <span data-ttu-id="def17-234">Wenn Sie **Am**auswählen, geben Sie den spezifischen Tag der Woche im Monat an, an dem der Auftragszeitplan ausgeführt wird, und wie oft der Auftragszeitplan wiederholt werden soll (in Monaten).</span><span class="sxs-lookup"><span data-stu-id="def17-234">If you select **The**, select the specific day of the week within the month that you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="def17-235">Wenn Sie beispielsweise möchten, dass der Auftragszeitplan jeden zweiten Monat am letzten Wochentag ausgeführt werden soll, wählen Sie **Tag** und in der ersten Liste **Letzter** und in der zweiten Liste **Wochentag** aus, und geben Sie in das letzte Feld „2“ ein.</span><span class="sxs-lookup"><span data-stu-id="def17-235">For example, if you want the job schedule to run on the last weekday of the month every other month, select **Day**, select **last** from the first list and **weekday** from the second list, and then enter "2" in the last box.</span></span> <span data-ttu-id="def17-236">Sie können auch **erster**, **zweiter**, **dritter**oder **vierter**sowie bestimmte Wochentage (z.B. Sonntag oder Mittwoch) aus den ersten beiden Listen auswählen.</span><span class="sxs-lookup"><span data-stu-id="def17-236">You can also select **first**, **second**, **third**, or **fourth**, as well as specific weekdays (for example: Sunday or Wednesday) from the first two lists.</span></span> <span data-ttu-id="def17-237">Beachten Sie, dass die größte im letzten Feld zulässige Zahl „99“ ist.</span><span class="sxs-lookup"><span data-stu-id="def17-237">Please note that the largest number allowed in the last box is "99".</span></span>  
  
        2.  <span data-ttu-id="def17-238">Geben Sie unter **Häufigkeit pro Tag**an, wie oft der Auftragszeitplan an dem Tag wiederholt werden soll, an dem der Auftragszeitplan ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="def17-238">Under **Daily frequency**, specify how often the job schedule repeats on the day the job schedule runs:</span></span>  
  
            -   <span data-ttu-id="def17-239">Wenn Sie **Einmalig um**auswählen, geben Sie im Feld **Einmalig um** die spezifische Tageszeit ein, zu der der Auftragszeitplan ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="def17-239">If you select **Occurs once at**, enter the specific time of day when the job schedule should run in the **Occurs once at** box.</span></span> <span data-ttu-id="def17-240">Geben Sie die Stunde, Minute und Sekunde des Tages sowie AM oder PM ein.</span><span class="sxs-lookup"><span data-stu-id="def17-240">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
            -   <span data-ttu-id="def17-241">Wenn Sie **Alle**auswählen, geben Sie an, wie oft der Auftragszeitplan an dem unter **Häufigkeit**ausgewählten Tag ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="def17-241">If you select **Occurs every**, specify how often the job schedule runs during the day chosen under **Frequency**.</span></span> <span data-ttu-id="def17-242">Wenn Sie z.B. möchten, dass der Auftragszeitplan am Tag seiner Ausführung alle 2 Stunden wiederholt wird, wählen Sie **Alle** aus, geben in das erste Feld „2“ ein und wählen dann in der Liste **Stunde(n)** aus.</span><span class="sxs-lookup"><span data-stu-id="def17-242">For example, if you want the job schedule to repeat every 2 hours during the day that the job schedule is run, select **Occurs every**, enter "2" in the first box, and then select **hour(s)** from the list.</span></span> <span data-ttu-id="def17-243">Aus dieser Liste können Sie auch **Minute(n)** und **Sekunde(n)** auswählen.</span><span class="sxs-lookup"><span data-stu-id="def17-243">From this list you can also select **minute(s)** and **second(s)**.</span></span> <span data-ttu-id="def17-244">Beachten Sie, dass die größte im ersten Feld zulässige Zahl „100“ ist.</span><span class="sxs-lookup"><span data-stu-id="def17-244">Please note that the largest number allowed in the first box is "100".</span></span>  
  
                 <span data-ttu-id="def17-245">Geben Sie im Feld **Start** die Zeit ein, zu der die Ausführung des Auftragszeitplans beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="def17-245">In the **Starting at** box, enter the time that the job schedule should start running.</span></span> <span data-ttu-id="def17-246">Geben Sie im Feld **Ende** die Zeit ein, zu der die Ausführung des Auftragszeitplans enden soll.</span><span class="sxs-lookup"><span data-stu-id="def17-246">In the **Ending at** box, enter the time that the job schedule should stop repeating.</span></span> <span data-ttu-id="def17-247">Geben Sie die Stunde, Minute und Sekunde des Tages sowie AM oder PM ein.</span><span class="sxs-lookup"><span data-stu-id="def17-247">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
        3.  <span data-ttu-id="def17-248">Geben Sie unter **Dauer**in **Startdatum**das Datum ein, an dem die Ausführung des Auftragszeitplans beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="def17-248">Under **Duration**, in **Start date**, enter the date that you want the job schedule to start running.</span></span> <span data-ttu-id="def17-249">Wählen Sie **Enddatum** oder **Kein Enddatum** aus, um anzugeben, wann die Ausführung des Auftragszeitplans beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="def17-249">Select **End date** or **No end date** to indicate when the job schedule should stop running.</span></span> <span data-ttu-id="def17-250">Wenn Sie **Enddatum**auswählen, geben Sie das Datum ein, an dem die Ausführung des Auftragszeitplans beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="def17-250">If you select **End date**, enter the date that you want to job schedule to stop running.</span></span>  
  
    5.  <span data-ttu-id="def17-251">Wenn Sie **Einmal**auswählen, geben Sie unter **Einmalig**in das Feld **Datum** das Datum ein, an dem der Auftragszeitplan ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="def17-251">If you select **One Time**, under **One-time occurrence**, in the **Date** box, enter the date that the job schedule will be run.</span></span> <span data-ttu-id="def17-252">Geben Sie im Feld **Uhrzeit** die Zeit ein, zu der der Auftragszeitplan ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="def17-252">In the **Time** box, enter the time that the job schedule will be run.</span></span> <span data-ttu-id="def17-253">Geben Sie die Stunde, Minute und Sekunde des Tages sowie AM oder PM ein.</span><span class="sxs-lookup"><span data-stu-id="def17-253">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
    6.  <span data-ttu-id="def17-254">Überprüfen Sie unter **Zusammenfassung**im Feld **Beschreibung**, ob alle Auftragszeitplaneinstellungen richtig sind.</span><span class="sxs-lookup"><span data-stu-id="def17-254">Under **Summary**, in **Description**, verify that all job schedule settings are correct.</span></span>  
  
    7.  <span data-ttu-id="def17-255">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="def17-255">Click **OK**.</span></span>  
  
     <span data-ttu-id="def17-256">Nach Fertigstellen dieser Seite klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="def17-256">After completing this page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="def17-257">Erweitern Sie auf der Seite **Zusammenfassung der Überprüfung** unter **Überprüfen Sie Ihre Auswahl**alle verfügbaren Optionen, um zu überprüfen, ob alle Partitionseinstellungen richtig sind.</span><span class="sxs-lookup"><span data-stu-id="def17-257">On the **Review Summary** page, under **Review your selections**, expand all available options to verify that all partition settings are correct.</span></span> <span data-ttu-id="def17-258">Klicken Sie auf **Fertig stellen**, wenn alle Einstellungen richtig sind.</span><span class="sxs-lookup"><span data-stu-id="def17-258">If everything is as expected, click **Finish**.</span></span>  
  
9. <span data-ttu-id="def17-259">Auf der Seite **Status des Assistenten zum Erstellen von Partitionen** können Sie Statusinformationen zu den Aktionen des Assistenten zum Erstellen von Partitionen überwachen.</span><span class="sxs-lookup"><span data-stu-id="def17-259">On the **Create Partition Wizard Progress** page, monitor status information about the actions of the Create Partition Wizard.</span></span> <span data-ttu-id="def17-260">Je nach den im Assistenten ausgewählten Optionen enthält diese Seite eine oder mehrere Aktionen.</span><span class="sxs-lookup"><span data-stu-id="def17-260">Depending on the options that you selected in the wizard, the progress page might contain one or more actions.</span></span> <span data-ttu-id="def17-261">Im oberen Feld werden der Gesamtstatus des Assistenten und die Anzahl der empfangenen Status-, Fehler- und Warnmeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="def17-261">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
     <span data-ttu-id="def17-262">Die folgenden Optionen sind auf der Seite **Status des Assistenten zum Erstellen von Partitionen** verfügbar:</span><span class="sxs-lookup"><span data-stu-id="def17-262">The following options are available on the **Create Partition Wizard Progress** page:</span></span>  
  
     <span data-ttu-id="def17-263">**Details**</span><span class="sxs-lookup"><span data-stu-id="def17-263">**Details**</span></span>  
     <span data-ttu-id="def17-264">Stellt für jede vom Assistenten ausgeführte Aktion Informationen zur Aktion, zum Status und zu den zurückgegebenen Meldungen bereit.</span><span class="sxs-lookup"><span data-stu-id="def17-264">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
     <span data-ttu-id="def17-265">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="def17-265">**Action**</span></span>  
     <span data-ttu-id="def17-266">Gibt den Typ und den Namen jeder Aktion an.</span><span class="sxs-lookup"><span data-stu-id="def17-266">Specifies the type and name of each action.</span></span>  
  
     <span data-ttu-id="def17-267">**Status**</span><span class="sxs-lookup"><span data-stu-id="def17-267">**Status**</span></span>  
     <span data-ttu-id="def17-268">Gibt an, ob für die Aktion des Assistenten insgesamt der Wert **Erfolg** oder der Wert **Fehler**zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="def17-268">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
     <span data-ttu-id="def17-269">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="def17-269">**Message**</span></span>  
     <span data-ttu-id="def17-270">Stellt alle vom Prozess zurückgegebenen Fehler- oder Warnmeldungen bereit.</span><span class="sxs-lookup"><span data-stu-id="def17-270">Provides any error or warning messages that are returned from the process.</span></span>  
  
     <span data-ttu-id="def17-271">**Report**</span><span class="sxs-lookup"><span data-stu-id="def17-271">**Report**</span></span>  
     <span data-ttu-id="def17-272">Erstellt einen Bericht mit den Ergebnissen des Assistenten zum Erstellen von Partitionen.</span><span class="sxs-lookup"><span data-stu-id="def17-272">Creates a report that contains the results of the Create Partition Wizard.</span></span> <span data-ttu-id="def17-273">Die Optionen sind **Bericht anzeigen**, **Bericht in Datei speichern**, **Bericht in Zwischenablage kopieren**und **Bericht als E-Mail senden**.</span><span class="sxs-lookup"><span data-stu-id="def17-273">The options are **View Report**, **Save Report to File**, **Copy Report to Clipboard**, and **Send Report as Email**.</span></span>  
  
     <span data-ttu-id="def17-274">**Bericht anzeigen**</span><span class="sxs-lookup"><span data-stu-id="def17-274">**View Report**</span></span>  
     <span data-ttu-id="def17-275">Öffnet das Dialogfeld **Bericht anzeigen** , das einen Textbericht zum Fortschritt des Assistenten zum Erstellen von Partitionen enthält.</span><span class="sxs-lookup"><span data-stu-id="def17-275">Opens the **View Report** dialog box, which contains a text report of the progress of the Create Partition Wizard.</span></span>  
  
     <span data-ttu-id="def17-276">**Bericht in Datei speichern**</span><span class="sxs-lookup"><span data-stu-id="def17-276">**Save Report to File**</span></span>  
     <span data-ttu-id="def17-277">Öffnet das Dialogfeld **Bericht speichern unter** .</span><span class="sxs-lookup"><span data-stu-id="def17-277">Opens the **Save Report As** dialog box.</span></span>  
  
     <span data-ttu-id="def17-278">**Bericht in Zwischenablage kopieren**</span><span class="sxs-lookup"><span data-stu-id="def17-278">**Copy Report to Clipboard**</span></span>  
     <span data-ttu-id="def17-279">Kopiert die Ergebnisse aus dem Statusbericht des Assistenten in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="def17-279">Copies the results of the wizard's progress report to the Clipboard.</span></span>  
  
     <span data-ttu-id="def17-280">**Bericht als E-Mail senden**</span><span class="sxs-lookup"><span data-stu-id="def17-280">**Send Report as Email**</span></span>  
     <span data-ttu-id="def17-281">Kopiert die Ergebnisse aus dem Statusbericht des Assistenten in eine E-Mail.</span><span class="sxs-lookup"><span data-stu-id="def17-281">Copies the results of the wizard's progress report into an email message.</span></span>  
  
     <span data-ttu-id="def17-282">Nach Abschluss dieser Schritte klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="def17-282">When complete, click **Close**.</span></span>  
  
 <span data-ttu-id="def17-283">Vom Assistenten zum Erstellen von Partitionen werden die Partitionsfunktion und das -schema erstellt, und anschließend wird die Partitionierung auf die angegebene Tabelle angewendet.</span><span class="sxs-lookup"><span data-stu-id="def17-283">The Create Partition Wizard creates the partition function and scheme and then applies the partitioning to the specified table.</span></span> <span data-ttu-id="def17-284">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf die Tabelle und wählen Sie **Eigenschaften**aus, um die Tabellenpartitionierung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="def17-284">To verify the table partitioning, in Object Explorer, right-click the table and select **Properties**.</span></span> <span data-ttu-id="def17-285">Klicken Sie auf die Seite **Speicherung** .</span><span class="sxs-lookup"><span data-stu-id="def17-285">Click the **Storage** page.</span></span> <span data-ttu-id="def17-286">Auf der Seite werden Informationen, beispielsweise der Name der Partitionsfunktion und das -schema sowie die Anzahl an Partitionen, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="def17-286">The page displays information such as the name of the partition function and scheme and the number of partitions.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="def17-287">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="def17-287">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-partitioned-table"></a><span data-ttu-id="def17-288">So erstellen Sie eine partitionierte Tabelle</span><span class="sxs-lookup"><span data-stu-id="def17-288">To create a partitioned table</span></span>  
  
1.  <span data-ttu-id="def17-289">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="def17-289">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="def17-290">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="def17-290">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="def17-291">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="def17-291">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="def17-292">Im Beispiel werden neue Dateigruppen, eine Partitionsfunktion und ein Partitionsschema erstellt.</span><span class="sxs-lookup"><span data-stu-id="def17-292">The example creates new filegroups, a partition function, and a partition scheme.</span></span> <span data-ttu-id="def17-293">Eine neue Tabelle wird mit dem Partitionsschema erstellt, das als Speicherort angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="def17-293">A new table is created with the partition scheme specified as the storage location.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Adds four new filegroups to the AdventureWorks2012 database  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test1fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test2fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test3fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test4fg;   
  
    -- Adds one file for each filegroup.  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test1dat1,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t1dat1.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test1fg;  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test2dat2,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t2dat2.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test2fg;  
    GO  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test3dat3,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t3dat3.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test3fg;  
    GO  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test4dat4,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t4dat4.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test4fg;  
    GO  
    -- Creates a partition function called myRangePF1 that will partition a table into four partitions  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
        AS RANGE LEFT FOR VALUES (1, 100, 1000) ;  
    GO  
    -- Creates a partition scheme called myRangePS1 that applies myRangePF1 to the four filegroups created above  
    CREATE PARTITION SCHEME myRangePS1  
        AS PARTITION myRangePF1  
        TO (test1fg, test2fg, test3fg, test4fg) ;  
    GO  
    -- Creates a partitioned table called PartitionTable that uses myRangePS1 to partition col1  
    CREATE TABLE PartitionTable (col1 int PRIMARY KEY, col2 char(10))  
        ON myRangePS1 (col1) ;  
    GO  
    ```  
  
#### <a name="to-determine-if-a-table-is-partitioned"></a><span data-ttu-id="def17-294">So bestimmen Sie, ob eine Tabelle partitioniert ist</span><span class="sxs-lookup"><span data-stu-id="def17-294">To determine if a table is partitioned</span></span>  
  
1.  <span data-ttu-id="def17-295">Die folgende Abfrage gibt mindestens eine Zeile zurück, wenn die `PartitionTable` -Tabelle partitioniert ist.</span><span class="sxs-lookup"><span data-stu-id="def17-295">The following query returns one or more rows if the table `PartitionTable` is partitioned.</span></span> <span data-ttu-id="def17-296">Wenn die Tabelle nicht partitioniert ist, werden keine Zeilen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="def17-296">If the table is not partitioned, no rows are returned.</span></span>  
  
    ```  
    SELECT *   
    FROM sys.tables AS t   
    JOIN sys.indexes AS i   
        ON t.[object_id] = i.[object_id]   
        AND i.[type] IN (0,1)   
    JOIN sys.partition_schemes ps   
        ON i.data_space_id = ps.data_space_id   
    WHERE t.name = 'PartitionTable';   
    GO  
    ```  
  
#### <a name="to-determine-the-boundary-values-for-a-partitioned-table"></a><span data-ttu-id="def17-297">Sie definieren Sie Begrenzungswerte für eine partitionierte Tabelle</span><span class="sxs-lookup"><span data-stu-id="def17-297">To determine the boundary values for a partitioned table</span></span>  
  
1.  <span data-ttu-id="def17-298">Die folgende Abfrage gibt die Begrenzungswerte für jede Partition in der `PartitionTable` -Tabelle zurück.</span><span class="sxs-lookup"><span data-stu-id="def17-298">The following query returns the boundary values for each partition in the `PartitionTable` table.</span></span>  
  
    ```  
    SELECT t.name AS TableName, i.name AS IndexName, p.partition_number, p.partition_id, i.data_space_id, f.function_id, f.type_desc, r.boundary_id, r.value AS BoundaryValue   
    FROM sys.tables AS t  
    JOIN sys.indexes AS i  
        ON t.object_id = i.object_id  
    JOIN sys.partitions AS p  
        ON i.object_id = p.object_id AND i.index_id = p.index_id   
    JOIN  sys.partition_schemes AS s   
        ON i.data_space_id = s.data_space_id  
    JOIN sys.partition_functions AS f   
        ON s.function_id = f.function_id  
    LEFT JOIN sys.partition_range_values AS r   
        ON f.function_id = r.function_id and r.boundary_id = p.partition_number  
    WHERE t.name = 'PartitionTable' AND i.type <= 1  
    ORDER BY p.partition_number;  
    ```  
  
#### <a name="to-determine-the-partition-column-for-a-partitioned-table"></a><span data-ttu-id="def17-299">So definieren Sie die Partitionsspalte für eine partitionierte Tabelle</span><span class="sxs-lookup"><span data-stu-id="def17-299">To determine the partition column for a partitioned table</span></span>  
  
1.  <span data-ttu-id="def17-300">Die folgende Abfrage gibt den Namen der Partitionierungsspalte für die Tabelle zurück.</span><span class="sxs-lookup"><span data-stu-id="def17-300">The following query returns the name of the partitioning column for table.</span></span> <span data-ttu-id="def17-301">[https://login.microsoftonline.com/consumers/](`PartitionTable`).</span><span class="sxs-lookup"><span data-stu-id="def17-301">`PartitionTable`.</span></span>  
  
    ```  
    SELECT   
        t.[object_id] AS ObjectID   
        , t.name AS TableName   
        , ic.column_id AS PartitioningColumnID   
        , c.name AS PartitioningColumnName   
    FROM sys.tables AS t   
    JOIN sys.indexes AS i   
        ON t.[object_id] = i.[object_id]   
        AND i.[type] <= 1 -- clustered index or a heap   
    JOIN sys.partition_schemes AS ps   
        ON ps.data_space_id = i.data_space_id   
    JOIN sys.index_columns AS ic   
        ON ic.[object_id] = i.[object_id]   
        AND ic.index_id = i.index_id   
        AND ic.partition_ordinal >= 1 -- because 0 = non-partitioning column   
    JOIN sys.columns AS c   
        ON t.[object_id] = c.[object_id]   
        AND ic.column_id = c.column_id   
    WHERE t.name = 'PartitionTable' ;   
    GO  
    ```  
  
 <span data-ttu-id="def17-302">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="def17-302">For more information, see:</span></span>  
  
-   [<span data-ttu-id="def17-303">ALTER DATABASE-Optionen für Dateien und Dateigruppen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="def17-303">ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options)  
  
-   [<span data-ttu-id="def17-304">CREATE PARTITION FUNCTION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="def17-304">CREATE PARTITION FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-partition-function-transact-sql)  
  
-   [<span data-ttu-id="def17-305">CREATE PARTITION SCHEME &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="def17-305">CREATE PARTITION SCHEME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-partition-scheme-transact-sql)  
  
-   [<span data-ttu-id="def17-306">CREATE TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="def17-306">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)  
  
  
