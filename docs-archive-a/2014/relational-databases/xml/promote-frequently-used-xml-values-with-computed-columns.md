---
title: Heraufstufen häufig verwendeter XML-Werte mit berechneten Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- promoting properties [XML in SQL Server]
- property promotion [XML in SQL Server]
ms.assetid: f5111896-c2fd-4209-b500-f2baa45489ad
author: rothja
ms.author: jroth
ms.openlocfilehash: bfb83b7772ffd92eab7087db11e4c3ffd96afa47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717542"
---
# <a name="promote-frequently-used-xml-values-with-computed-columns"></a><span data-ttu-id="61258-102">Heraufstufen häufig verwendeter XML-Werte mit berechneten Spalten</span><span class="sxs-lookup"><span data-stu-id="61258-102">Promote Frequently Used XML Values with Computed Columns</span></span>
  <span data-ttu-id="61258-103">Wenn Abfragen in erster Linie nur für eine geringe Anzahl von Element- und Attributwerten ausgeführt werden, kann es sinnvoll sein, diese Mengen in relationale Spalten heraufzustufen.</span><span class="sxs-lookup"><span data-stu-id="61258-103">If queries are made principally on a small number of element and attribute values, you may want to promote those quantities into relational columns.</span></span> <span data-ttu-id="61258-104">Dies ist nützlich, wenn Abfragen für einen kleinen Teil der XML-Daten ausgegeben werden, während die gesamte XML-Instanz abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="61258-104">This is helpful when queries are issued on a small part of the XML data while the whole XML instance is retrieved.</span></span> <span data-ttu-id="61258-105">Das Erstellen eines XML-Indexes für die XML-Spalte ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="61258-105">Creating an XML index on the XML column is not required.</span></span> <span data-ttu-id="61258-106">Stattdessen kann die heraufgestufte Spalte indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="61258-106">Instead, the promoted column can be indexed.</span></span> <span data-ttu-id="61258-107">Um die heraufgestufte Spalte zu verwenden, müssen Abfragen geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="61258-107">Queries must be written to use the promoted column.</span></span> <span data-ttu-id="61258-108">Das heißt, der Abfrageoptimierer richtet die Abfragen für die XML-Spalte nicht erneut an die heraufgestufte Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="61258-108">That is, the query optimizer does not target again the queries on the XML column to the promoted column.</span></span>  
  
 <span data-ttu-id="61258-109">Die heraufgestufte Spalte kann entweder eine berechnete Spalte in derselben Tabelle oder eine getrennte, benutzerverwaltete Spalte in einer Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="61258-109">The promoted column can be a computed column in the same table or it can be a separate, user-maintained column in a table.</span></span> <span data-ttu-id="61258-110">Dies ist ausreichend, wenn Singleton-Werte aus jeder XML-Instanz heraufgestuft werden.</span><span class="sxs-lookup"><span data-stu-id="61258-110">This is sufficient when singleton values are promoted from each XML instance.</span></span> <span data-ttu-id="61258-111">Allerdings müssen Sie für mehrwertige Eigenschaften eine getrennte Tabelle für die Eigenschaft erstellen, was im folgenden Abschnitt beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="61258-111">However, for multi-valued properties, you have to create a separate table for the property, as described in the following section.</span></span>  
  
## <a name="computed-column-based-on-the-xml-data-type"></a><span data-ttu-id="61258-112">Berechnete Spalte auf der Basis des xml-Datentyps</span><span class="sxs-lookup"><span data-stu-id="61258-112">Computed Column Based on the xml Data Type</span></span>  
 <span data-ttu-id="61258-113">Eine berechnete Spalte kann mithilfe einer benutzerdefinierten Funktion erstellt werden, die- `xml` Datentyp Methoden aufruft.</span><span class="sxs-lookup"><span data-stu-id="61258-113">A computed column can be created by using a user-defined function that invokes `xml` data type methods.</span></span> <span data-ttu-id="61258-114">Der Typ der berechneten Spalte kann jeder SQL-Typ sein, einschließlich XML.</span><span class="sxs-lookup"><span data-stu-id="61258-114">The type of the computed column can be any SQL type, including XML.</span></span> <span data-ttu-id="61258-115">Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="61258-115">This is illustrated in the following example.</span></span>  
  
### <a name="example-computed-column-based-on-the-xml-data-type-method"></a><span data-ttu-id="61258-116">Beispiel: Berechnete Spalten basierend auf der XML-Datentypmethode</span><span class="sxs-lookup"><span data-stu-id="61258-116">Example: Computed Column Based on the xml Data Type Method</span></span>  
 <span data-ttu-id="61258-117">Erstellen Sie die benutzerdefinierte Funktion für die ISBN-Nummer eines Buchs:</span><span class="sxs-lookup"><span data-stu-id="61258-117">Create the user-defined function for a book ISBN number:</span></span>  
  
```  
CREATE FUNCTION udf_get_book_ISBN (@xData xml)  
RETURNS varchar(20)  
BEGIN  
   DECLARE @ISBN   varchar(20)  
   SELECT @ISBN = @xData.value('/book[1]/@ISBN', 'varchar(20)')  
   RETURN @ISBN   
END  
```  
  
 <span data-ttu-id="61258-118">Fügen Sie der Tabelle eine berechnete Spalte für die ISBN hinzu:</span><span class="sxs-lookup"><span data-stu-id="61258-118">Add a computed column to the table for the ISBN:</span></span>  
  
```  
ALTER TABLE      T  
ADD   ISBN AS dbo.udf_get_book_ISBN(xCol)  
```  
  
 <span data-ttu-id="61258-119">Die berechnete Spalte kann auf gewöhnliche Weise indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="61258-119">The computed column can be indexed in the usual way.</span></span>  
  
### <a name="example-queries-on-a-computed-column-based-on-xml-data-type-methods"></a><span data-ttu-id="61258-120">Beispiel: Abfragen für eine berechnete Spalte basierend auf XML-Datentypmethoden</span><span class="sxs-lookup"><span data-stu-id="61258-120">Example: Queries on a Computed Column Based on xml Data Type Methods</span></span>  
 <span data-ttu-id="61258-121">So erhalten Sie das <`book`>-Element, dessen ISBN 0-7356-1588-2 ist:</span><span class="sxs-lookup"><span data-stu-id="61258-121">To obtain the <`book`> whose ISBN is 0-7356-1588-2:</span></span>  
  
```  
SELECT xCol  
FROM   T  
WHERE  xCol.exist('/book/@ISBN[. = "0-7356-1588-2"]') = 1  
```  
  
 <span data-ttu-id="61258-122">Die Abfrage für die XML-Spalte kann so umgeschrieben werden, dass sie die berechnete Spalte verwendet:</span><span class="sxs-lookup"><span data-stu-id="61258-122">The query on the XML column can be rewritten to use the computed column as follows:</span></span>  
  
```  
SELECT xCol  
FROM   T  
WHERE  ISBN = '0-7356-1588-2'  
```  
  
 <span data-ttu-id="61258-123">Sie können eine benutzerdefinierte Funktion erstellen, um den `xml` Datentyp und eine berechnete Spalte mithilfe der benutzerdefinierten Funktion zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="61258-123">You can create a user-defined function to return the `xml` data type and a computed column by using the user-defined function.</span></span> <span data-ttu-id="61258-124">Allerdings können Sie keinen XML-Index für die berechnete XML-Spalte erstellen.</span><span class="sxs-lookup"><span data-stu-id="61258-124">However, you cannot create an XML index on the computed, XML column.</span></span>  
  
## <a name="creating-property-tables"></a><span data-ttu-id="61258-125">Erstellen von Eigenschaftentabellen</span><span class="sxs-lookup"><span data-stu-id="61258-125">Creating Property Tables</span></span>  
 <span data-ttu-id="61258-126">Wenn Sie einige der mehrwertigen Eigenschaften aus Ihren XML-Daten in eine oder mehrere Tabellen heraufstufen möchten, erstellen Sie Indizes für diese Tabellen und richten Sie Ihre Abfrage erneut so aus, dass sie diese Indizes verwenden.</span><span class="sxs-lookup"><span data-stu-id="61258-126">You may want to promote some of the multivalued properties from your XML data into one or more tables, create indexes on those tables, and target again your queries to use them.</span></span> <span data-ttu-id="61258-127">Ein typisches Szenario hierfür ist eine Situation, in der eine kleine Anzahl von Eigenschaften den Großteil Ihrer Abfragearbeitsauslastung abdeckt.</span><span class="sxs-lookup"><span data-stu-id="61258-127">A typical scenario is one in which a small number of properties covers most of your query workload.</span></span> <span data-ttu-id="61258-128">Sie können folgendermaßen vorgehen:</span><span class="sxs-lookup"><span data-stu-id="61258-128">You can do the following:</span></span>  
  
-   <span data-ttu-id="61258-129">Erstellen Sie eine oder mehrere Tabellen, die die mehrwertigen Eigenschaften aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="61258-129">Create one or more tables to hold the multivalued properties.</span></span> <span data-ttu-id="61258-130">Sie könnten praktischerweise so vorgehen, dass Sie eine Eigenschaft pro Tabelle speichern und den Primärschlüssel der Basistabelle in den Eigenschaftentabellen speichern, um einen Rückwärtsjoin mit der Basistabelle zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="61258-130">You may find it convenient to store one property per table and duplicate the primary key of the base table in the property tables for back joining with the base table.</span></span>  
  
-   <span data-ttu-id="61258-131">Wenn Sie die relative Reihenfolge der Eigenschaften beibehalten möchten, müssen Sie eine getrennte Spalte für die relative Reihenfolge einführen.</span><span class="sxs-lookup"><span data-stu-id="61258-131">If you want to maintain the relative order of the properties, you have to introduce a separate column for the relative order.</span></span>  
  
-   <span data-ttu-id="61258-132">Erstellen Sie Trigger für die XML-Spalte, um die Eigenschaftentabellen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="61258-132">Create triggers on the XML column to maintain the property tables.</span></span> <span data-ttu-id="61258-133">Führen Sie innerhalb der Trigger einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="61258-133">Within the triggers, do one of the following:</span></span>  
  
    -   <span data-ttu-id="61258-134">Verwenden `xml` Sie Datentyp Methoden, wie z. b. **Nodes ()** und **value ()**, um Zeilen der Eigenschaften Tabellen einzufügen und zu löschen.</span><span class="sxs-lookup"><span data-stu-id="61258-134">Use `xml` data type methods, such as **nodes()** and **value()**, to insert and delete rows of the property tables.</span></span>  
  
    -   <span data-ttu-id="61258-135">Erstellen Sie Streaming-Tabellenwertfunktionen in CLR (Common Language Runtime), um Zeilen der Eigenschaftentabellen einzufügen oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="61258-135">Create streaming table-valued functions in the common language runtime (CLR) to insert and delete rows of the property tables.</span></span>  
  
    -   <span data-ttu-id="61258-136">Schreiben Sie Abfragen für den SQL-Zugriff auf die Eigenschaftentabellen und für den XML-Zugriff auf die XML-Spalte in der Basistabelle, wodurch Joins zwischen den Tabellen mithilfe ihres Primärschlüssels erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="61258-136">Write queries for SQL access to the property tables and for XML access to the XML column in the base table, with joins between the tables by using their primary key.</span></span>  
  
### <a name="example-create-a-property-table"></a><span data-ttu-id="61258-137">Beispiel: Erstellen einer Eigenschaftentabelle</span><span class="sxs-lookup"><span data-stu-id="61258-137">Example: Create a Property Table</span></span>  
 <span data-ttu-id="61258-138">Angenommen, Sie wollen den ersten Vornamen des Autors heraufstufen.</span><span class="sxs-lookup"><span data-stu-id="61258-138">For illustration, assume that you want to promote the first name of the authors.</span></span> <span data-ttu-id="61258-139">Bücher weisen einen oder mehrere Autoren auf, sodass der Vorname eine mehrwertige Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="61258-139">Books have one or more authors, so that first name is a multivalued property.</span></span> <span data-ttu-id="61258-140">Jeder Vorname ist in einer getrennten Zeile einer Eigenschaftentabelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="61258-140">Each first name is stored in a separate row of a property table.</span></span> <span data-ttu-id="61258-141">Der Primärschlüssel der Basistabelle wird in die Eigenschaftentabelle dupliziert, um einen Rückwärtsjoin zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="61258-141">The primary key of the base table is duplicated in the property table for back join.</span></span>  
  
```  
create table tblPropAuthor (propPK int, propAuthor varchar(max))  
```  
  
### <a name="example-create-a-user-defined-function-to-generate-a-rowset-from-an-xml-instance"></a><span data-ttu-id="61258-142">Beispiel: Erstellen einer benutzerdefinierten Funktion zum Generieren eines Rowsets aus einer XML-Instanz</span><span class="sxs-lookup"><span data-stu-id="61258-142">Example: Create a User-defined Function to Generate a Rowset from an XML Instance</span></span>  
 <span data-ttu-id="61258-143">Die folgende Tabellenwertfunktion (udf_XML2Table) akzeptiert einen Primärschlüsselwert und eine XML-Instanz.</span><span class="sxs-lookup"><span data-stu-id="61258-143">The following table-valued function, udf_XML2Table, accepts a primary key value and an XML instance.</span></span> <span data-ttu-id="61258-144">Sie ruft den Vornamen aller Autoren aus den <`book`>-Elementen ab und gibt ein Rowset mit Paaren aus Primärschlüssel und Vorname zurück.</span><span class="sxs-lookup"><span data-stu-id="61258-144">It retrieves the first name of all authors of the <`book`> elements and returns a rowset of primary key, first name pairs.</span></span>  
  
```  
create function udf_XML2Table (@pk int, @xCol xml)  
returns @ret_Table table (propPK int, propAuthor varchar(max))  
with schemabinding  
as  
begin  
      insert into @ret_Table   
      select @pk, nref.value('.', 'varchar(max)')  
      from   @xCol.nodes('/book/author/first-name') R(nref)  
      return  
end  
```  
  
### <a name="example-create-triggers-to-populate-a-property-table"></a><span data-ttu-id="61258-145">Beispiel: Erstellen von Triggern zum Auffüllen einer Eigenschaftentabelle</span><span class="sxs-lookup"><span data-stu-id="61258-145">Example: Create Triggers to Populate a Property Table</span></span>  
 <span data-ttu-id="61258-146">Der insert-Trigger bewirkt das Einfügen von Zeilen in die Eigenschaftentabelle:</span><span class="sxs-lookup"><span data-stu-id="61258-146">The insert trigger inserts rows into the property table:</span></span>  
  
```  
create trigger trg_docs_INS on T for insert  
as  
      declare @wantedXML xml  
      declare @FK int  
      select @wantedXML = xCol from inserted  
      select @FK = PK from inserted  
  
   insert into tblPropAuthor  
   select * from dbo.udf_XML2Table(@FK, @wantedXML)  
```  
  
 <span data-ttu-id="61258-147">Der delete-Trigger löscht die Zeilen aus der Eigenschaftentabelle und richtet sich dabei nach dem Primärschlüsselwert der gelöschten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="61258-147">The delete trigger deletes the rows from the property table based on the primary key value of the deleted rows:</span></span>  
  
```  
create trigger trg_docs_DEL on T for delete  
as  
   declare @FK int  
   select @FK = PK from deleted  
   delete tblPropAuthor where propPK = @FK  
```  
  
 <span data-ttu-id="61258-148">Der update-Trigger löscht die vorhandenen Zeilen in der Eigenschaftentabelle entsprechend der aktualisierten XML-Instanz und fügt neue Zeilen in die Eigenschaftentabelle ein:</span><span class="sxs-lookup"><span data-stu-id="61258-148">The update trigger deletes the existing rows in the property table corresponding to the updated XML instance and inserts new rows into the property table:</span></span>  
  
```  
create trigger trg_docs_UPD  
on T  
for update  
as  
if update(xCol) or update(pk)  
begin  
      declare @FK int  
      declare @wantedXML xml  
      select @FK = PK from deleted  
      delete tblPropAuthor where propPK = @FK  
  
   select @wantedXML = xCol from inserted  
   select @FK = pk from inserted  
  
   insert into tblPropAuthor   
      select * from dbo.udf_XML2Table(@FK, @wantedXML)  
end  
```  
  
### <a name="example-find-xml-instances-whose-authors-have-the-same-first-name"></a><span data-ttu-id="61258-149">Beispiel: Suchen nach XML-Instanzen, deren Autoren denselben Vornamen haben</span><span class="sxs-lookup"><span data-stu-id="61258-149">Example: Find XML Instances Whose Authors Have the Same First Name</span></span>  
 <span data-ttu-id="61258-150">Die Abfrage kann für die XML-Spalte geformt werden.</span><span class="sxs-lookup"><span data-stu-id="61258-150">The query can be formed on the XML column.</span></span> <span data-ttu-id="61258-151">Alternativ kann sie die Eigenschaftentabelle nach dem Vornamen "David" durchsuchen und einen Rückwärtsjoins mit der Basistabelle ausführen, um die XML-Instanz zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="61258-151">Alternatively, it can search the property table for first name "David" and perform a back join with the base table to return the XML instance.</span></span> <span data-ttu-id="61258-152">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="61258-152">For example:</span></span>  
  
```  
SELECT xCol   
FROM     T JOIN tblPropAuthor ON T.pk = tblPropAuthor.propPK  
WHERE    tblPropAuthor.propAuthor = 'David'  
```  
  
### <a name="example-solution-using-the-clr-streaming-table-valued-function"></a><span data-ttu-id="61258-153">Beispiel: Lösung mit der Streaming-Tabellenwertfunktion in CLR</span><span class="sxs-lookup"><span data-stu-id="61258-153">Example: Solution Using the CLR Streaming Table-valued Function</span></span>  
 <span data-ttu-id="61258-154">Diese Projektmappe umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="61258-154">This solution is made up of the following steps:</span></span>  
  
1.  <span data-ttu-id="61258-155">Definieren Sie eine CLR-Klasse (SqlReaderBase), die ISqlReader implementiert und eine Tabellenwert-Streaming-Ausgabe generiert, indem ein Pfadausdruck auf eine XML-Instanz angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="61258-155">Define a CLR class, SqlReaderBase, that implements ISqlReader and generates a streaming, table-valued output by applying a path expression on an XML instance.</span></span>  
  
2.  <span data-ttu-id="61258-156">Erstellen Sie ein Assembly und eine benutzerdefinierte Transact-SQL-Funktion, um die CLR-Klasse zu starten.</span><span class="sxs-lookup"><span data-stu-id="61258-156">Create an assembly and a Transact-SQL user-defined function to start the CLR class.</span></span>  
  
3.  <span data-ttu-id="61258-157">Definieren Sie die insert-, update- und delete-Trigger, indem Sie die benutzerdefinierte Funktion zum Verwalten einer Eigenschaftentabelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="61258-157">Define the insert, update, and delete triggers by using the user-defined function to maintain a property tables.</span></span>  
  
 <span data-ttu-id="61258-158">Dazu erstellen Sie zuerst die Streaming-CLR-Funktion.</span><span class="sxs-lookup"><span data-stu-id="61258-158">To do this, you first create the streaming CLR function.</span></span> <span data-ttu-id="61258-159">Der `xml` -Datentyp wird als verwaltete SQLXML-Klasse in ADO.net verfügbar gemacht und **CreateReader()** unterstützt die Methode "Methode", die einen XmlReader zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="61258-159">The `xml` data type is exposed as a managed class SqlXml in ADO.NET and supports the **CreateReader()** method that returns an XmlReader.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61258-160">Der Beispielcode in diesem Abschnitt verwendet XPathDocument und XPathNavigator.</span><span class="sxs-lookup"><span data-stu-id="61258-160">The example code in this section uses XPathDocument and XPathNavigator.</span></span> <span data-ttu-id="61258-161">Diese zwingen Sie, alle XML-Dokumente in den Arbeitsspeicher zu laden.</span><span class="sxs-lookup"><span data-stu-id="61258-161">These force you to load all the XML documents into memory.</span></span> <span data-ttu-id="61258-162">Wenn Sie ähnlichen Code in Ihrer Anwendung verwenden, um mehrere große XML-Dokumente zu verarbeiten, ist dieser Code nicht skalierbar.</span><span class="sxs-lookup"><span data-stu-id="61258-162">If you are using similar code in your application to process several large XML documents, this code is not scalable.</span></span> <span data-ttu-id="61258-163">Halten Sie stattdessen die Speicherbelegung gering, und verwenden Sie wenn möglich Streaming-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="61258-163">Instead, keep memory allocations small and use streaming interfaces whenever possible.</span></span> <span data-ttu-id="61258-164">Weitere Informationen zur Leistung finden Sie unter [Architektur der CLR-Integration](../../database-engine/dev-guide/architecture-of-clr-integration.md).</span><span class="sxs-lookup"><span data-stu-id="61258-164">For more information about performance, see [Architecture of CLR Integration](../../database-engine/dev-guide/architecture-of-clr-integration.md).</span></span>  
  
```  
public class c_streaming_xml_tvf {  
   public static ISqlReader streaming_xml_tvf   
(SqlXml xmlDoc, string pathExpression) {  
      return (new TestSqlReaderBase (xmlDoc, pathExpression));  
   }  
}  
  
// Class that implements ISqlReader  
public class TestSqlReaderBase : ISqlReader {  
XPathNodeIterator m_iterator;           
   public SqlChars FirstName;  
// Metadata for current resultset  
private SqlMetaData[] m_rgSqlMetaData;        
  
   public TestSqlReaderBase (SqlXml xmlDoc, string pathExpression) {     
      // Variables for XPath navigation  
      XPathDocument xDoc;  
      XPathNavigator xNav;  
      XPathExpression xPath;  
  
      // Set sql metadata  
      m_rgSqlMetaData = new SqlMetaData[1];  
      m_rgSqlMetaData[0] = new SqlMetaData ("FirstName",    
SqlDbType.NVarChar,50);     
  
      //Set up the Navigator  
      if (!xmlDoc.IsNull)  
          xDoc = new XPathDocument (xmlDoc.CreateReader());  
      else  
          xDoc = new XPathDocument ();  
      xNav = xDoc.CreateNavigator();  
      xPath = xNav.Compile (pathExpression);  
      m_iterator = xNav.Select(xPath);  
   }  
   public bool Read() {  
      bool moreRows = true;  
      if (moreRows = m_iterator.MoveNext())  
         FirstName = new SqlChars (m_iterator.Current.Value);  
      return moreRows;  
   }  
}  
```  
  
 <span data-ttu-id="61258-165">Erstellen Sie als Nächstes eine Assembly und eine benutzerdefinierte [!INCLUDE[tsql](../../includes/tsql-md.md)] -Funktion – SQL_streaming_xml_tvf (nicht dargestellt) –, die der CLR-Funktion streaming_xml_tvf entspricht.</span><span class="sxs-lookup"><span data-stu-id="61258-165">Next, create an assembly and a [!INCLUDE[tsql](../../includes/tsql-md.md)] user-defined function, SQL_streaming_xml_tvf (not shown), that corresponds to the CLR function, streaming_xml_tvf.</span></span> <span data-ttu-id="61258-166">Die benutzerdefinierte Funktion wird zum Definieren der Tabellenwertfunktion CLR_udf_XML2Table verwendet, mit der das Rowset generiert wird:</span><span class="sxs-lookup"><span data-stu-id="61258-166">The user-defined function is used to define the table-valued function, CLR_udf_XML2Table, for rowset generation:</span></span>  
  
```  
create function CLR_udf_XML2Table (@pk int, @xCol xml)  
returns @ret_Table table (FK int, FirstName varchar(max))  
with schemabinding  
as  
begin  
      insert into @ret_Table   
   select @pk, FirstName   
   FROM   SQL_streaming_xml_tvf (@xCol, '/book/author/first-name')  
      return  
end  
```  
  
 <span data-ttu-id="61258-167">Definieren Sie schließlich die Trigger wie im Beispiel "Erstellen von Triggern zum Auffüllen einer Eigenschaftentabelle", ersetzen Sie dabei jedoch udf_XML2Table durch die CLR_udf_XML2Table-Funktion.</span><span class="sxs-lookup"><span data-stu-id="61258-167">Finally, define triggers as shown in the example, "Create triggers to populate a property table", but replace udf_XML2Table with the CLR_udf_XML2Table function.</span></span> <span data-ttu-id="61258-168">Der insert-Trigger ist im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="61258-168">The insert trigger is shown in the following example:</span></span>  
  
```  
create trigger CLR_trg_docs_INS on T for insert  
as  
   declare @wantedXML xml  
   declare @FK int  
   select @wantedXML = xCol from inserted  
   select @FK = PK from inserted  
  
   insert into tblPropAuthor  
      select *  
   from    dbo.CLR_udf_XML2Table(@FK, @wantedXML)  
```  
  
 <span data-ttu-id="61258-169">Der delete-Trigger ist identisch mit der Nicht-CLR-Version.</span><span class="sxs-lookup"><span data-stu-id="61258-169">The delete trigger is identical to the non-CLR version.</span></span> <span data-ttu-id="61258-170">Dagegen ist beim update-Trigger lediglich die Funktion udf_XML2Table() durch CLR_udf_XML2Table() ersetzt.</span><span class="sxs-lookup"><span data-stu-id="61258-170">However, the update trigger just replaces the function udf_XML2Table() with CLR_udf_XML2Table().</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61258-171">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61258-171">See Also</span></span>  
 [<span data-ttu-id="61258-172">Verwenden von XML in berechneten Spalten</span><span class="sxs-lookup"><span data-stu-id="61258-172">Use XML in Computed Columns</span></span>](use-xml-in-computed-columns.md)  
  
  
