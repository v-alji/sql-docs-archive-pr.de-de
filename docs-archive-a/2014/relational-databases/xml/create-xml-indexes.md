---
title: Erstellen von XML-Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- indexes [XML in SQL Server]
- XML indexes [SQL Server], creating
ms.assetid: 6ecac598-355d-4408-baf7-1b2e8d4cf7c1
author: rothja
ms.author: jroth
ms.openlocfilehash: 9e7800193222b8c9060fee1b247cc5585654cde4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722602"
---
# <a name="create-xml-indexes"></a><span data-ttu-id="fafe5-102">Erstellen von XML-Indizes</span><span class="sxs-lookup"><span data-stu-id="fafe5-102">Create XML Indexes</span></span>
  <span data-ttu-id="fafe5-103">In diesem Thema wird beschrieben, wie primäre und sekundäre XML-Indizes erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fafe5-103">This topic describes how to create primary and secondary XML indexes.</span></span>  
  
## <a name="creating-a-primary-xml-index"></a><span data-ttu-id="fafe5-104">Erstellen eines primären XML-Indexes</span><span class="sxs-lookup"><span data-stu-id="fafe5-104">Creating a Primary XML Index</span></span>  
 <span data-ttu-id="fafe5-105">Um einen primären XML-Index zu erstellen, verwenden Sie die DDL-Anweisung [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fafe5-105">To create a primary XML index, use the [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement.</span></span> <span data-ttu-id="fafe5-106">Nicht alle Optionen, die für Nicht-XML-Indizes verfügbar sind, werden für XML-Indizes unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fafe5-106">Not all options available for non-XML indexes are supported on XML indexes.</span></span>  
  
 <span data-ttu-id="fafe5-107">Beachten Sie beim Erstellen eines XML-Indexes Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fafe5-107">Note the following when you are creating an XML index:</span></span>  
  
-   <span data-ttu-id="fafe5-108">Damit ein primärer XML-Index erstellt werden kann, muss die Tabelle, die die zu indizierende XML-Spalte enthält (als Basistabelle bezeichnet), einen gruppierten Index für den Primärschlüssel enthalten.</span><span class="sxs-lookup"><span data-stu-id="fafe5-108">To create a primary XML index, the table that contains the XML column being indexed, called the base table, must have a clustered index on the primary key.</span></span> <span data-ttu-id="fafe5-109">Auf diese Weise wird sichergestellt, dass der primäre XML-Index mithilfe des gleichen Partitionierungsschemas und der gleichen Partitionierungsfunktion partitioniert werden kann, wenn die Basistabelle partitioniert ist.</span><span class="sxs-lookup"><span data-stu-id="fafe5-109">This makes sure that if the base table is partitioned, the primary XML index can be partitioned by using the same partitioning scheme and partitioning function.</span></span>  
  
-   <span data-ttu-id="fafe5-110">Wenn ein XML-Index vorhanden ist, kann der gruppierte Primärschlüssel der Tabelle nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fafe5-110">If an XML index exists, the clustered, primary key of the table cannot be modified.</span></span> <span data-ttu-id="fafe5-111">Sie müssen alle XML-Indizes für die Tabelle löschen, bevor Sie den Primärschlüssel ändern können.</span><span class="sxs-lookup"><span data-stu-id="fafe5-111">You will have to drop all XML indexes on the table before modifying the primary key.</span></span>  
  
-   <span data-ttu-id="fafe5-112">Ein primärer XML-Index kann für eine einzelne Spalte vom Typ `xml` erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fafe5-112">A primary XML index can be created on a single `xml` type column.</span></span> <span data-ttu-id="fafe5-113">Sie können keinen anderen Indextyp mit der Spalte vom Typ XML als Schlüsselspalte erstellen.</span><span class="sxs-lookup"><span data-stu-id="fafe5-113">You cannot create any other type of index with the XML type column as a key column.</span></span> <span data-ttu-id="fafe5-114">Sie können jedoch die Spalte vom Typ `xml` in einen Nicht-XML-Index einschließen.</span><span class="sxs-lookup"><span data-stu-id="fafe5-114">However, you can include the `xml` L type column in a non-XML index.</span></span> <span data-ttu-id="fafe5-115">Jede Spalte vom Typ `xml` in einer Tabelle kann ihren eigenen primären XML-Index aufweisen.</span><span class="sxs-lookup"><span data-stu-id="fafe5-115">Each `xml` type column in a table can have its own primary XML index.</span></span> <span data-ttu-id="fafe5-116">Es ist jedoch nur ein primärer XML-Index pro Spalte vom Typ `xml` zulässig.</span><span class="sxs-lookup"><span data-stu-id="fafe5-116">However, only one primary XML index per `xml` type column is permitted.</span></span>  
  
-   <span data-ttu-id="fafe5-117">XML-Indizes werden im gleichen Namespace wie Nicht-XML-Indizes gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fafe5-117">XML indexes exist in the same namespace as non-XML indexes.</span></span> <span data-ttu-id="fafe5-118">Aus diesem Grund dürfen ein XML-Index und ein Nicht-XML-Index für die gleiche Tabelle nicht den gleichen Namen besitzen.</span><span class="sxs-lookup"><span data-stu-id="fafe5-118">Therefore, you cannot have an XML index and a non-XML index on the same table with the same name.</span></span>  
  
-   <span data-ttu-id="fafe5-119">Die Optionen IGNORE_DUP_KEY- und ONLINE werden für XML-Indizes immer auf OFF festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fafe5-119">IGNORE_DUP_KEY and ONLINE options of are always set to OFF for XML indexes.</span></span> <span data-ttu-id="fafe5-120">Sie können diese Optionen mit einem Wert von OFF angeben.</span><span class="sxs-lookup"><span data-stu-id="fafe5-120">You can specify these options with a value of OFF.</span></span>  
  
-   <span data-ttu-id="fafe5-121">Die Dateigruppen- oder Partitionierungsinformationen der Benutzertabelle werden auf den XML-Index angewendet.</span><span class="sxs-lookup"><span data-stu-id="fafe5-121">The filegroup or partitioning information of the user table is applied to the XML index.</span></span> <span data-ttu-id="fafe5-122">Benutzer können diese nicht separat für einen XML-Index angeben.</span><span class="sxs-lookup"><span data-stu-id="fafe5-122">Users cannot specify these separately on an XML index.</span></span>  
  
-   <span data-ttu-id="fafe5-123">Die DROP_EXISTING-Indexoption kann einen primären XML-Index löschen und einen neuen primären XML-Index erstellen oder einen sekundären XML-Index löschen und einen neuen sekundären XML-Index erstellen.</span><span class="sxs-lookup"><span data-stu-id="fafe5-123">The DROP_EXISTING index option can drop a primary XML index and create a new primary XML index, or drop a secondary XML index and create a new secondary XML index.</span></span> <span data-ttu-id="fafe5-124">Mit dieser Option kann jedoch nicht ein sekundärer XML-Index gelöscht werden, um einen neuen primären XML-Index zu erstellen oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="fafe5-124">However, this option cannot drop a secondary XML index to create a new primary XML index or vice versa.</span></span>  
  
-   <span data-ttu-id="fafe5-125">Für die Namen primärer XML-Indizes gelten die gleichen Einschränkungen wie für Sichtnamen.</span><span class="sxs-lookup"><span data-stu-id="fafe5-125">Primary XML index names have the same restrictions as view names.</span></span>  
  
 <span data-ttu-id="fafe5-126">Sie können keinen XML-Index für eine `xml` Spalte vom Typ in einer Sicht, für eine **Tabellen** Wert Variable mit `xml` Typspalten oder `xml` Typvariablen erstellen.</span><span class="sxs-lookup"><span data-stu-id="fafe5-126">You cannot create an XML index on an `xml` type column in a view, on a **table** valued variable with `xml` type columns, or `xml` type variables.</span></span>  
  
-   <span data-ttu-id="fafe5-127">Wenn Sie eine Spalte vom Typ `xml` mithilfe der Option ALTER TABLE ALTER COLUMN aus nicht typisiertem in typisiertes XML oder umgekehrt ändern möchten, sollte kein XML-Index für die Spalte vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="fafe5-127">To change an `xml` type column from untyped to typed XML, or vice versa, by using the ALTER TABLE ALTER COLUMN option, no XML index on the column should exist.</span></span> <span data-ttu-id="fafe5-128">Wenn ein XML-Index vorhanden ist, muss dieser gelöscht werden, bevor der Änderungsversuch des Spaltentyps unternommen wird.</span><span class="sxs-lookup"><span data-stu-id="fafe5-128">If one does exist, it must be dropped before the column type change is tried.</span></span>  
  
-   <span data-ttu-id="fafe5-129">Die Option ARITHABORT muss auf ON festgelegt werden, wenn ein XML-Index erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="fafe5-129">The option ARITHABORT must be set to ON when an XML index is created.</span></span> <span data-ttu-id="fafe5-130">Zum Abfragen, Einfügen, Löschen oder Aktualisieren von Werten in der XML-Spalte mithilfe der Methoden des XML-Datentyps muss die gleiche Option für die Verbindung festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fafe5-130">To query, insert, delete, or update values in the XML column using XML data type methods, the same option must be set on the connection.</span></span> <span data-ttu-id="fafe5-131">Wenn dies nicht der Fall ist, schlagen die Methoden des XML-Datentyps fehl.</span><span class="sxs-lookup"><span data-stu-id="fafe5-131">If it is not, the XML data type methods will fail.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fafe5-132">Informationen zu einem XML-Index finden Sie in den Katalogsichten.</span><span class="sxs-lookup"><span data-stu-id="fafe5-132">Information about an XML index can be found in catalog views.</span></span> <span data-ttu-id="fafe5-133">**sp_helpindex** wird jedoch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fafe5-133">However, **sp_helpindex** is not supported.</span></span> <span data-ttu-id="fafe5-134">Beispiele weiter unten in diesem Abschnitt veranschaulichen, wie die Katalogsichten zum Ermitteln von XML-Indexinformationen abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="fafe5-134">Examples provided later in this topic show how to query the catalog views to find XML index information.</span></span>  
  
 <span data-ttu-id="fafe5-135">Bei Erstellen oder Neuerstellen eines primären XML-Indexes für eine Spalte des XML-Datentyps, die Werte der XML-Schematypen **xs:date** oder **xs:dateTime** (oder andere Untertypen dieser Typen) mit einer kleineren Jahresangabe als 1 enthält, kann der Index in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] und späteren Versionen nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fafe5-135">When creating or recreating a primary XML index on an XML data type column that contains values of the XML Schema types **xs:date** or **xs:dateTime** (or any subtypes of these types) that have a year of less than 1, the index creation will fail in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="fafe5-136">ließ diese Werte zu. Dieses Problem kann daher auftreten, wenn Indizes in einer mit [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]generierten Datenbank erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fafe5-136">allowed these values, so this problem can occur when creating indexes in a database generated in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="fafe5-137">Weitere Informationen finden Sie unter [Vergleichen von typisiertem XML mit nicht typisiertem XML](../xml/compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="fafe5-137">For more information, see [Compare Typed XML to Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md).</span></span>  
  
### <a name="example-creating-a-primary-xml-index"></a><span data-ttu-id="fafe5-138">Beispiel: Erstellen eines primären XML-Indexes</span><span class="sxs-lookup"><span data-stu-id="fafe5-138">Example: Creating a Primary XML Index</span></span>  
 <span data-ttu-id="fafe5-139">In den meisten Beispielen wird Tabelle T (pk INT PRIMARY KEY, xCol XML) mit einer nicht typisierten XML-Spalte verwendet.</span><span class="sxs-lookup"><span data-stu-id="fafe5-139">Table T (pk INT PRIMARY KEY, xCol XML) with an untyped XML column is used in most of the examples.</span></span> <span data-ttu-id="fafe5-140">Diese können auf einfache Weise zu typisiertem XML erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="fafe5-140">These can be extended to typed XML in a straightforward way.</span></span> <span data-ttu-id="fafe5-141">Aus Gründen der Vereinfachung werden die Abfragen für XML-Dateninstanzen beschrieben, wie das im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="fafe5-141">For simplicity, queries are described for XML data instances as shown in the following:</span></span>  
  
```  
<book genre="security" publicationdate="2002" ISBN="0-7356-1588-2">  
   <title>Writing Secure Code</title>  
   <author>  
      <first-name>Michael</first-name>  
      <last-name>Howard</last-name>  
   </author>  
   <author>  
      <first-name>David</first-name>  
      <last-name>LeBlanc</last-name>  
   </author>  
   <price>39.99</price>  
</book>  
```  
  
 <span data-ttu-id="fafe5-142">Die folgende Anweisung erstellt einen XML-Index mit der Bezeichnung idx_xCol für die XML-Spalte xCol der Tabelle T:</span><span class="sxs-lookup"><span data-stu-id="fafe5-142">The following statement creates an XML index, called idx_xCol, on the XML column xCol of table T:</span></span>  
  
```  
CREATE PRIMARY XML INDEX idx_xCol on T (xCol)  
```  
  
## <a name="creating-a-secondary-xml-index"></a><span data-ttu-id="fafe5-143">Erstellen eines sekundären XML-Indexes</span><span class="sxs-lookup"><span data-stu-id="fafe5-143">Creating a Secondary XML Index</span></span>  
 <span data-ttu-id="fafe5-144">Verwenden Sie die DDL-Anweisung [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)], um sekundäre XML-Indizes zu erstellen und den Typ des gewünschten sekundären XML-Indexes anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fafe5-144">Use the [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement to create secondary XML indexes and specify the type of the secondary XML index that you want.</span></span>  
  
 <span data-ttu-id="fafe5-145">Beachten Sie beim Erstellen sekundärer XML-Indizes Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fafe5-145">Note the following when you are creating secondary XML indexes:</span></span>  
  
-   <span data-ttu-id="fafe5-146">Alle Indizierungsoptionen, die für einen nicht gruppierten Index gelten, sind mit Ausnahme von IGNORE_DUP_KEY und ONLINE für sekundäre XML-Indizes zulässig.</span><span class="sxs-lookup"><span data-stu-id="fafe5-146">All indexing options that apply to a nonclustered index, except IGNORE_DUP_KEY and ONLINE, are permitted on secondary XML indexes.</span></span> <span data-ttu-id="fafe5-147">Die beiden Optionen müssen für sekundäre XML-Indizes immer auf OFF festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="fafe5-147">The two options must always be set to OFF for secondary XML indexes.</span></span>  
  
-   <span data-ttu-id="fafe5-148">Die sekundären Indizes werden ebenso wie der primäre XML-Index partitioniert.</span><span class="sxs-lookup"><span data-stu-id="fafe5-148">The secondary indexes are partitioned just like the primary XML index.</span></span>  
  
-   <span data-ttu-id="fafe5-149">DROP_EXISTING kann einen sekundären Index für die Benutzertabelle löschen und einen anderen sekundären Index für die Benutzertabelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="fafe5-149">DROP_EXISTING can drop a secondary index on the user table and create another secondary index on the user table.</span></span>  
  
 <span data-ttu-id="fafe5-150">Sie können die **sys.xml_indexes** -Katalogsicht abfragen, um XML-Indexinformationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fafe5-150">You can query the **sys.xml_indexes** catalog view to retrieve XML index information.</span></span> <span data-ttu-id="fafe5-151">Beachten Sie, dass die **secondary_type_desc** -Spalte in der **sys.xml_indexes** -Katalogsicht den Typ des sekundären Indexes bereitstellt:</span><span class="sxs-lookup"><span data-stu-id="fafe5-151">Note that the **secondary_type_desc** column in the **sys.xml_indexes** catalog view provides the type of secondary index:</span></span>  
  
```  
SELECT  *   
FROM    sys.xml_indexes;  
```  
  
 <span data-ttu-id="fafe5-152">Der zurückgegebene Wert in der **secondary_type_desc** -Spalte kann NULL, PATH, VALUE oder PROPERTY sein.</span><span class="sxs-lookup"><span data-stu-id="fafe5-152">The values returned in the **secondary_type_desc** column can be NULL, PATH, VALUE, or PROPERTY.</span></span> <span data-ttu-id="fafe5-153">Für den primären Index lautet der zurückgegebene Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="fafe5-153">For the primary XML index, the value returned is NULL.</span></span>  
  
### <a name="example-creating-secondary-xml-indexes"></a><span data-ttu-id="fafe5-154">Beispiel: Erstellen sekundärer XML-Indizes</span><span class="sxs-lookup"><span data-stu-id="fafe5-154">Example: Creating Secondary XML Indexes</span></span>  
 <span data-ttu-id="fafe5-155">Das folgende Beispiel zeigt, wie sekundäre XML-Indizes erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fafe5-155">The following example illustrates how secondary XML indexes are created.</span></span> <span data-ttu-id="fafe5-156">Im Beispiel werden außerdem Informationen zu den von Ihnen erstellten XML-Indizes bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fafe5-156">The example also shows information about the XML indexes that you created.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML);  
GO  
-- Create primary index.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol);  
GO  
-- Create secondary indexes (PATH, VALUE, PROPERTY).  
CREATE XML INDEX PIdx_T_XmlCol_PATH ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR PATH;  
GO  
CREATE XML INDEX PIdx_T_XmlCol_VALUE ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR VALUE;  
GO  
CREATE XML INDEX PIdx_T_XmlCol_PROPERTY ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR PROPERTY;  
GO  
```  
  
 <span data-ttu-id="fafe5-157">Sie können die `sys.xml_indexes` -Katalogsicht abfragen, um XML-Indexinformationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fafe5-157">You can query the `sys.xml_indexes` to retrieve XML indexes information.</span></span> <span data-ttu-id="fafe5-158">Der Typ wird in der `secondary_type_desc` -Spalte des zweiten Indizes bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fafe5-158">The `secondary_type_desc` column provides the secondary index type.</span></span>  
  
```  
SELECT  *   
FROM    sys.xml_indexes;  
```  
  
 <span data-ttu-id="fafe5-159">Sie können auch die Katalogsicht nach Indexinformationen abfragen.</span><span class="sxs-lookup"><span data-stu-id="fafe5-159">You can also query the catalog view for index information.</span></span>  
  
```  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T');  
```  
  
 <span data-ttu-id="fafe5-160">Sie können Beispieldaten hinzufügen und anschließend die XML-Indexinformationen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="fafe5-160">You can add sample data and then review the XML index information.</span></span>  
  
```  
INSERT INTO T VALUES (1,  
'<doc id="123">  
<sections>  
<section num="2">  
<heading>Background</heading>  
</section>  
<section num="3">  
<heading>Sort</heading>  
</section>  
<section num="4">  
<heading>Search</heading>  
</section>  
</sections>  
</doc>');  
GO  
-- Check XML index information.  
SELECT *  
FROM   sys.dm_db_index_physical_stats (db_id(), object_id('T'), NULL, NULL, 'DETAILED');  
GO  
-- Space usage of primary XML index  
DECLARE @index_id int;  
SELECT  @index_id = i.index_id  
FROM    sys.xml_indexes i   
WHERE   i.name = 'PIdx_T_XmlCol' and object_name(i.object_id) = 'T';  
  
SELECT *  
FROM sys.dm_db_index_physical_stats (db_id(), object_id('T') , @index_id, DEFAULT, 'DETAILED');  
go  
--- Space usage of secondary XML index (for example PATH secondary index)  PIdx_T_XmlCol_PATH  
DECLARE @index_id int;  
SELECT  @index_id = i.index_id   
FROM    sys.xml_indexes i   
WHERE  i.name = 'PIdx_T_XmlCol_PATH' and object_name(i.object_id) = 'T';  
  
SELECT *  
FROM sys.dm_db_index_physical_stats (db_id(), object_id('T') , @index_id, DEFAULT, 'DETAILED');  
go  
  
-- Space usage of all secondary XML indexes for a particular table  
SELECT i.name, object_name(i.object_id), stats.*   
FROM   sys.dm_db_index_physical_stats (db_id(), object_id('T'), NULL, DEFAULT, 'DETAILED') stats  
JOIN sys.xml_indexes i ON (stats.object_id = i.object_id and stats.index_id = i.index_id)  
WHERE secondary_type is not null;  
-- Drop secondary indexes.  
DROP INDEX PIdx_T_XmlCol_PATH ON T;  
GO  
DROP INDEX PIdx_T_XmlCol_VALUE ON T;  
GO  
DROP INDEX PIdx_T_XmlCol_PROPERTY ON T;  
GO  
-- Drop primary index.  
DROP INDEX PIdx_T_XmlCol ON T;  
-- Drop table T.  
DROP TABLE T;  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="fafe5-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fafe5-161">See Also</span></span>  
 <span data-ttu-id="fafe5-162">[XML-Indizes &#40;SQL Server&#41;](xml-indexes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fafe5-162">[XML Indexes &#40;SQL Server&#41;](xml-indexes-sql-server.md) </span></span>  
 [<span data-ttu-id="fafe5-163">XML-Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fafe5-163">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
