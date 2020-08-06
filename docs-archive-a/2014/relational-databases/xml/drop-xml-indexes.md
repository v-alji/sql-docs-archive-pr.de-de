---
title: Löschen von XML-Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- removing indexes
- dropping indexes
- XML indexes [SQL Server], dropping
ms.assetid: 7591ebea-34af-4925-8553-b2adb5b487c2
author: rothja
ms.author: jroth
ms.openlocfilehash: b7d4621cf2182b4587b12665a1cfe10ddbe0db3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608434"
---
# <a name="drop-xml-indexes"></a><span data-ttu-id="bccf3-102">Löschen von XML-Indizes</span><span class="sxs-lookup"><span data-stu-id="bccf3-102">Drop XML Indexes</span></span>
  <span data-ttu-id="bccf3-103">Die [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung kann zum Löschen vorhandener primärer oder sekundärer XML-Indizes und Nicht-XML-Indizes verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bccf3-103">The [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] statement can be used to drop existing primary or secondary XML and non-XML indexes.</span></span> <span data-ttu-id="bccf3-104">Die DROP INDEX-Optionen gelten jedoch nicht für XML-Indizes.</span><span class="sxs-lookup"><span data-stu-id="bccf3-104">However, no options of DROP INDEX apply to XML indexes.</span></span> <span data-ttu-id="bccf3-105">Wenn Sie den primären XML-Index löschen, werden sämtliche vorhandenen sekundären Indizes ebenfalls gelöscht.</span><span class="sxs-lookup"><span data-stu-id="bccf3-105">If you drop the primary XML index, any secondary indexes that are present are also deleted.</span></span>  
  
 <span data-ttu-id="bccf3-106">Die DROP-Syntax mit *TableName.IndexName* ist veraltet und wird für XML-Indizes nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bccf3-106">The DROP syntax with *TableName.IndexName* is being phased out and is not supported for XML indexes.</span></span>  
  
## <a name="example-creating-and-dropping-a-primary-xml-index"></a><span data-ttu-id="bccf3-107">Beispiel: Erstellen und Löschen eines primären XML-Index</span><span class="sxs-lookup"><span data-stu-id="bccf3-107">Example: Creating and Dropping a Primary XML Index</span></span>  
 <span data-ttu-id="bccf3-108">Im folgenden Beispiel wird ein XML-Index für eine Spalte vom Typ `xml` erstellt:</span><span class="sxs-lookup"><span data-stu-id="bccf3-108">In the following example, an XML index is created on an `xml` type column.</span></span>  
  
```  
DROP TABLE T  
GO  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
-- Create Primary XML index   
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol)  
GO  
-- Verify the index creation.   
-- Note index type is 3 for xml indexes.  
-- Note the type 3 is index on XML type.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'   
-- Drop the index.  
DROP INDEX PIdx_T_XmlCol ON T  
```  
  
 <span data-ttu-id="bccf3-109">Beim Löschen einer Tabelle werden auch XML-Indizes für diese automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="bccf3-109">When a table is dropped, all the XML indexes on it are also automatically dropped.</span></span> <span data-ttu-id="bccf3-110">Eine XML-Spalte kann jedoch nicht aus einer Tabelle gelöscht werden, wenn ein XML-Index für die Spalte vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bccf3-110">However, an XML column cannot be dropped from a table if an XML index exists on the column.</span></span>  
  
 <span data-ttu-id="bccf3-111">Im folgenden Beispiel wird ein XML-Index für eine Spalte vom Typ `xml` erstellt:</span><span class="sxs-lookup"><span data-stu-id="bccf3-111">In the following example, an XML index is created on an `xml` type column.</span></span> <span data-ttu-id="bccf3-112">Weitere Informationen finden Sie unter [Vergleichen von typisiertem XML mit nicht typisiertem XML](../xml/compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bccf3-112">For more information, see [Compare Typed XML to Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md).</span></span>  
  
```  
CREATE TABLE TestTable(  
 Col1 int primary key,   
 Col2 xml (Production.ProductDescriptionSchemaCollection))   
GO  
```  
  
 <span data-ttu-id="bccf3-113">Nun können Sie einen primären XML-Index für `Co12`erstellen:</span><span class="sxs-lookup"><span data-stu-id="bccf3-113">Now, you can create a primary XML index on `Co12`.</span></span>  
  
```  
CREATE PRIMARY XML INDEX PIdx_TestTable_Col2   
ON TestTable(Col2)  
GO  
```  
  
## <a name="example-creating-an-xml-index-by-using-the-drop_existing-index-option"></a><span data-ttu-id="bccf3-114">Beispiel: Erstellen eines XML-Index mithilfe der DROP_EXISTING-Indexoption</span><span class="sxs-lookup"><span data-stu-id="bccf3-114">Example: Creating an XML Index by Using the DROP_EXISTING Index Option</span></span>  
 <span data-ttu-id="bccf3-115">Im folgenden Beispiel wird ein XML-Index für eine Spalte (`XmlColx`) erstellt.</span><span class="sxs-lookup"><span data-stu-id="bccf3-115">In the following example, an XML index is created on a column (`XmlColx`).</span></span> <span data-ttu-id="bccf3-116">Anschließend wird ein weiterer XML-Index mit dem gleichen Namen für eine andere Spalte (`XmlColy`) erstellt.</span><span class="sxs-lookup"><span data-stu-id="bccf3-116">Then, another XML index with the same name is created on a different column, (`XmlColy`).</span></span> <span data-ttu-id="bccf3-117">Da die Option `DROP_EXISTING` angegeben wird, wird der vorhandene XML-Index für (`XmlColx)` gelöscht und ein neuer XML-Index für (`XmlColy`) erstellt.</span><span class="sxs-lookup"><span data-stu-id="bccf3-117">Because the `DROP_EXISTING` option is specified, the existing XML index on (`XmlColx)` is dropped and a new XML index on (`XmlColy`) is created.</span></span>  
  
```  
DROP TABLE T  
GO  
CREATE TABLE T(Col1 int primary key, XmlColx xml, XmlColy xml)  
GO  
-- Create XML index on XmlColx.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlColx)  
GO  
-- Create same name XML index on XmlColy.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlColy)   
WITH (DROP_EXISTING = ON)  
-- Verify the index is created on XmlColy.d.  
SELECT sc.name   
FROM   sys.xml_indexes si inner join sys.index_columns sic   
ON     sic.object_id=si.object_id and sic.index_id=si.index_id  
INNER  join sys.columns sc on sc.object_id=sic.object_id   
AND    sc.column_id=sic.column_id  
WHERE  si.name='PIdx_T_XmlCol'   
AND    si.object_id=object_id('T')  
```  
  
 <span data-ttu-id="bccf3-118">Diese Abfrage gibt den Spaltennamen zurück, für den der angegebene XML-Index erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="bccf3-118">This query returns the column name on which the specified XML index is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bccf3-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bccf3-119">See Also</span></span>  
 [<span data-ttu-id="bccf3-120">XML-Indizes &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bccf3-120">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
