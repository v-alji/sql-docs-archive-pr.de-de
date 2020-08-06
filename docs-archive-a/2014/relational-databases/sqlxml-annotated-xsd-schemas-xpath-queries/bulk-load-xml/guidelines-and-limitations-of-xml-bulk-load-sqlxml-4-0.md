---
title: Richtlinien und Einschränkungen für XML-Massen laden (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML], about XML Bulk Load
- bulk load [SQLXML], about bulk load
ms.assetid: c5885d14-c7c1-47b3-a389-455e99a7ece1
author: rothja
ms.author: jroth
ms.openlocfilehash: 08c0020ac7b28702f5a573c6158ec9d50c735b2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619752"
---
# <a name="guidelines-and-limitations-of-xml-bulk-load-sqlxml-40"></a><span data-ttu-id="a2540-102">Richtlinien und Einschränkungen von XML-Massenladen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="a2540-102">Guidelines and Limitations of XML Bulk Load (SQLXML 4.0)</span></span>
  <span data-ttu-id="a2540-103">Wenn Sie XML-Massenladen verwenden, sollten Sie mit den folgenden Richtlinien und Einschränkungen vertraut sein:</span><span class="sxs-lookup"><span data-stu-id="a2540-103">When you use XML Bulk Load, you should be familiar with the following guidelines and limitations:</span></span>  
  
-   <span data-ttu-id="a2540-104">Inlineschemas werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a2540-104">Inline schemas are not supported.</span></span>  
  
     <span data-ttu-id="a2540-105">Wenn im XML-Quelldokument ein Inlineschema vorhanden ist, wird dieses Schema von XML-Massenladen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a2540-105">If you have an inline schema in the source XML document, XML Bulk Load ignores that schema.</span></span> <span data-ttu-id="a2540-106">Sie geben das Zuordnungsschema für XML-Massenladen außerhalb der XML-Daten an.</span><span class="sxs-lookup"><span data-stu-id="a2540-106">You specify the mapping schema for XML Bulk Load external to the XML data.</span></span> <span data-ttu-id="a2540-107">Sie können das Zuordnungsschema nicht mit dem **xmlns = "x:Schema"** -Attribut auf einem Knoten angeben.</span><span class="sxs-lookup"><span data-stu-id="a2540-107">You cannot specify the mapping schema at a node by using the **xmlns="x:schema"** attribute.</span></span>  
  
-   <span data-ttu-id="a2540-108">Es wird überprüft, ob ein XML-Dokument wohlgeformt ist, es wird jedoch nicht überprüft, ob es gültig ist.</span><span class="sxs-lookup"><span data-stu-id="a2540-108">An XML document is checked for being well-formed, but it is not validated.</span></span>  
  
     <span data-ttu-id="a2540-109">XML-Massen laden überprüft das XML-Dokument, um zu bestimmen, ob es wohl geformt ist, d. h., um sicherzustellen, dass der XML-Code den Syntax Anforderungen der XML 1,0-Empfehlung des World Wide Web Consortium entspricht.</span><span class="sxs-lookup"><span data-stu-id="a2540-109">XML Bulk Load checks the XML document to determine whether it is well-formed-that is, to ensure that the XML conforms to the syntax requirements of the World Wide Web Consortium's XML 1.0 recommendation.</span></span> <span data-ttu-id="a2540-110">Wenn das Dokument nicht wohlgeformt ist, wird die Verarbeitung durch XML-Massenladen abgebrochen und ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a2540-110">If the document is not well-formed, XML Bulk Load cancels processing and returns an error.</span></span> <span data-ttu-id="a2540-111">Die einzige Ausnahme hierbei stellen Dokumente dar, bei denen es sich um Fragmente handelt (wenn das Dokument beispielsweise kein einzelnes Stammelement aufweist). In diesem Fall wird das Dokument durch XML-Massenladen geladen.</span><span class="sxs-lookup"><span data-stu-id="a2540-111">The only exception to this is when the document is a fragment (for example, the document has no single root element), in which case XML Bulk Load will load the document.</span></span>  
  
     <span data-ttu-id="a2540-112">XML-Massenladen überprüft das Dokument nicht im Hinblick auf XML-Daten oder DTD-Schemas, die in der XML-Datendatei definiert sind oder auf die in der XML-Datendatei verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a2540-112">XML Bulk Load does not validate the document with respect to any XML-Data or DTD schema that is defined or referenced within the XML data file.</span></span> <span data-ttu-id="a2540-113">XML-Massenladen überprüft die XML-Datendatei auch nicht im Hinblick auf das bereitgestellte Zuordnungsschema.</span><span class="sxs-lookup"><span data-stu-id="a2540-113">In addition, XML Bulk Load does not validate the XML data file against the mapping schema supplied.</span></span>  
  
-   <span data-ttu-id="a2540-114">Alle XML-Prologinformationen werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a2540-114">Any XML prolog information is ignored.</span></span>  
  
     <span data-ttu-id="a2540-115">Beim XML-Massen laden werden alle Informationen vor und nach dem- \<root> Element im XML-Dokument ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a2540-115">XML Bulk Load ignores all the information before and after the \<root> element in the XML document.</span></span> <span data-ttu-id="a2540-116">XML-Massenladen ignoriert beispielsweise sämtliche XML-Deklarationen, internen DTD-Definitionen, externen DTD-Verweise, Kommentare usw.</span><span class="sxs-lookup"><span data-stu-id="a2540-116">For example, XML Bulk Load ignores any XML declarations, internal DTD definitions, external DTD references, comments, and so on.</span></span>  
  
-   <span data-ttu-id="a2540-117">Bei einem Zuordnungsschema, das eine Primärschlüssel-Fremdschlüssel-Beziehung zwischen zwei Tabellen (wie etwa zwischen den Tabellen Customer und CustOrder) definiert, muss die Tabelle mit dem Primärschlüssel im Schema zuerst beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="a2540-117">If you have a mapping schema that defines a primary key/foreign key relationship between two tables (such as between Customer and CustOrder), the table with the primary key must be described first in the schema.</span></span> <span data-ttu-id="a2540-118">Die Tabelle mit der Fremdschlüsselspalte muss später im Schema angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a2540-118">The table with the foreign key column must appear later in the schema.</span></span> <span data-ttu-id="a2540-119">Der Grund hierfür ist, dass die Reihenfolge, in der die Tabellen im Schema identifiziert werden, die Reihenfolge ist, in der Sie in die Datenbank geladen werden. Das folgende XDR-Schema erzeugt z. b. einen Fehler, wenn es beim XML-Massen Laden verwendet wird, da das- **\<Order>** Element vor dem-Element beschrieben wird **\<Customer>** .</span><span class="sxs-lookup"><span data-stu-id="a2540-119">The reason for this is that the order in which the tables are identified in the schema is the order that is used to load them into the database.For example, the following XDR schema will produce an error when it is used in XML Bulk Load because the **\<Order>** element is described before the **\<Customer>** element.</span></span> <span data-ttu-id="a2540-120">Die Spalte CustomerID in der Tabelle CustOrder ist eine Fremdschlüsselspalte, die auf die Primärschlüsselspalte CustomerID in der Tabelle Cust verweist.</span><span class="sxs-lookup"><span data-stu-id="a2540-120">The CustomerID column in CustOrder is a foreign key column that refers to the CustomerID primary key column in the Cust table.</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
            xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
            xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
        <ElementType name="Order" sql:relation="CustOrder" >  
          <AttributeType name="OrderID" />  
          <AttributeType name="CustomerID" />  
          <attribute type="OrderID" />  
          <attribute type="CustomerID" />  
        </ElementType>  
  
       <ElementType name="CustomerID" dt:type="int" />  
       <ElementType name="CompanyName" dt:type="string" />  
       <ElementType name="City" dt:type="string" />  
  
       <ElementType name="root" sql:is-constant="1">  
          <element type="Customers" />  
       </ElementType>  
       <ElementType name="Customers" sql:relation="Cust"   
                         sql:overflow-field="OverflowColumn"  >  
          <element type="CustomerID" sql:field="CustomerID" />  
          <element type="CompanyName" sql:field="CompanyName" />  
          <element type="City" sql:field="City" />  
          <element type="Order" >   
               <sql:relationship  
                   key-relation="Cust"  
                    key="CustomerID"  
                    foreign-key="CustomerID"  
                    foreign-relation="CustOrder" />  
          </element>  
       </ElementType>  
    </Schema>  
    ```  
  
-   <span data-ttu-id="a2540-121">Wenn im Schema keine Überlaufspalten mithilfe der `sql:overflow-field`-Anmerkung angegeben wurden, ignoriert XML-Massenladen Daten, die zwar im XML-Dokument vorhanden, im Zuordnungsschema jedoch nicht beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="a2540-121">If the schema does not specify overflow columns by using the `sql:overflow-field` annotation, XML Bulk Load ignores any data that is present in the XML document but is not described in the mapping schema.</span></span>  
  
     <span data-ttu-id="a2540-122">XML-Massenladen wendet das angegebene Zuordnungsschema an, sobald es im XML-Datenstrom auf bekannte Tags trifft.</span><span class="sxs-lookup"><span data-stu-id="a2540-122">XML Bulk Load applies the mapping schema that you have specified whenever it encounters known tags in the XML data stream.</span></span> <span data-ttu-id="a2540-123">XML-Massenladen ignoriert Daten, die zwar im XML-Dokument vorhanden, im Schema jedoch nicht beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="a2540-123">It ignores data that is present in the XML document but is not described in the schema.</span></span> <span data-ttu-id="a2540-124">Nehmen Sie beispielsweise an, Sie verfügen über ein Mapping-Schema, das ein- **\<Customer>** Element beschreibt.</span><span class="sxs-lookup"><span data-stu-id="a2540-124">For example, assume you have a mapping schema that describes a **\<Customer>** element.</span></span> <span data-ttu-id="a2540-125">Die XML-Datendatei verfügt über ein **\<AllCustomers>** Stammtag (das im Schema nicht beschrieben ist), das alle **\<Customer>** Elemente einschließt:</span><span class="sxs-lookup"><span data-stu-id="a2540-125">The XML data file has an **\<AllCustomers>** root tag (which is not described in the schema) that encloses all the **\<Customer>** elements:</span></span>  
  
    ```  
    <AllCustomers>  
      <Customer>...</Customer>  
      <Customer>...</Customer>  
       ...  
    </AllCustomers>  
    ```  
  
     <span data-ttu-id="a2540-126">In diesem Fall ignoriert XML-Massen laden das **\<AllCustomers>** -Element und beginnt mit der Zuordnung im- **\<Customer>** Element.</span><span class="sxs-lookup"><span data-stu-id="a2540-126">In this case, XML Bulk Load ignores the **\<AllCustomers>** element and begins mapping at the **\<Customer>** element.</span></span> <span data-ttu-id="a2540-127">XML-Massenladen ignoriert die Elemente, die zwar im XML-Dokument vorhanden, im Schema jedoch nicht beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="a2540-127">XML Bulk Load ignores the elements that are not described in the schema but are present in the XML document.</span></span>  
  
     <span data-ttu-id="a2540-128">Angenommen, eine andere XML-Quell Datendatei enthält- **\<Order>** Elemente.</span><span class="sxs-lookup"><span data-stu-id="a2540-128">Consider another XML source data file that contains **\<Order>** elements.</span></span> <span data-ttu-id="a2540-129">Diese Elemente sind im Zuordnungsschema nicht beschrieben:</span><span class="sxs-lookup"><span data-stu-id="a2540-129">These elements are not described in the mapping schema:</span></span>  
  
    ```  
    <AllCustomers>  
      <Customer>...</Customer>  
        <Order> ... </Order>  
        <Order> ... </Order>  
         ...  
      <Customer>...</Customer>  
        <Order> ... </Order>  
        <Order> ... </Order>  
         ...  
      ...  
    </AllCustomers>  
    ```  
  
     <span data-ttu-id="a2540-130">Beim XML-Massen laden werden diese **\<Order>** Elemente ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a2540-130">XML Bulk Load ignores these **\<Order>** elements.</span></span> <span data-ttu-id="a2540-131">Wenn Sie jedoch die-Anmerkung `sql:overflow-field` im Schema verwenden, um eine Spalte als Überlauf Spalte zu identifizieren, speichert XML-Massen laden alle nicht verbrauchten Daten in dieser Spalte.</span><span class="sxs-lookup"><span data-stu-id="a2540-131">But if you use the `sql:overflow-field`annotation in the schema to identify a column as an overflow column, XML Bulk Load stores all unconsumed data in this column.</span></span>  
  
-   <span data-ttu-id="a2540-132">CDATA-Abschnitte und Entitätsverweise werden vor dem Speichern in der Datenbank in das entsprechende Zeichenfolgenäquivalent übersetzt.</span><span class="sxs-lookup"><span data-stu-id="a2540-132">CDATA sections and entity references are translated to their string equivalents before they are stored in the database.</span></span>  
  
     <span data-ttu-id="a2540-133">In diesem Beispiel umschließt ein CDATA-Abschnitt den Wert für das- **\<City>** Element.</span><span class="sxs-lookup"><span data-stu-id="a2540-133">In this example, a CDATA section wraps the value for the **\<City>** element.</span></span> <span data-ttu-id="a2540-134">XML-Massen laden extrahiert den Zeichen folgen Wert ("NY"), bevor das **\<City>** Element in die Datenbank eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="a2540-134">XML Bulk Load extracts the string value ("NY") before it inserts the **\<City>** element into the database.</span></span>  
  
    ```  
    <City><![CDATA[NY]]> </City>  
    ```  
  
     <span data-ttu-id="a2540-135">XML-Massenladen behält Entitätsverweise nicht bei.</span><span class="sxs-lookup"><span data-stu-id="a2540-135">XML Bulk Load does not preserve entity references.</span></span>  
  
-   <span data-ttu-id="a2540-136">Wenn in einem Zuordnungsschema der Standardwert eines Attributs angegeben ist, verwendet XML-Massenladen dieses Attribut, auch wenn das Attribut in den XML-Quelldaten nicht enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a2540-136">If the mapping schema specifies the default value for an attribute and the XML source data does not contain that attribute, XML Bulk Load uses the default value.</span></span>  
  
     <span data-ttu-id="a2540-137">Das folgende XDR-Beispiel Schema weist dem **HireDate** -Attribut einen Standardwert zu:</span><span class="sxs-lookup"><span data-stu-id="a2540-137">The following sample XDR schema assigns a default value to the **HireDate** attribute:</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
            xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
            xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
       <ElementType name="root" sql:is-constant="1">  
          <element type="Customers" />  
       </ElementType>  
  
       <ElementType name="Customers" sql:relation="Cust3" >  
          <AttributeType name="CustomerID" dt:type="int"  />  
          <AttributeType name="HireDate"  default="2000-01-01" />  
          <AttributeType name="Salary"   />  
  
          <attribute type="CustomerID" sql:field="CustomerID" />  
          <attribute type="HireDate"   sql:field="HireDate"  />  
          <attribute type="Salary"     sql:field="Salary"    />  
       </ElementType>  
    </Schema>  
    ```  
  
     <span data-ttu-id="a2540-138">In diesen XML-Daten fehlt das **HireDate** -Attribut im zweiten **\<Customers>** Element.</span><span class="sxs-lookup"><span data-stu-id="a2540-138">In this XML data, the **HireDate** attribute is missing from the second **\<Customers>** element.</span></span> <span data-ttu-id="a2540-139">Wenn XML-Massen laden das zweite **\<Customers>** Element in die Datenbank einfügt, wird der im Schema angegebene Standardwert verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2540-139">When XML Bulk Load inserts the second **\<Customers>** element into the database, it uses the default value that is specified in the schema.</span></span>  
  
    ```  
    <ROOT>  
      <Customers CustomerID="1" HireDate="1999-01-01" Salary="10000" />  
      <Customers CustomerID="2" Salary="10000" />  
    </ROOT>  
    ```  
  
-   <span data-ttu-id="a2540-140">Die `sql:url-encode`-Anmerkung wird nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="a2540-140">The `sql:url-encode` annotation is not supported:</span></span>  
  
     <span data-ttu-id="a2540-141">Eine in der XML-Dateneingabe angegebene URL wird von Massenladen an diesem Speicherort nicht gelesen.</span><span class="sxs-lookup"><span data-stu-id="a2540-141">You cannot specify a URL in the XML data input and expect Bulk Load to read data from that location.</span></span>  
  
     <span data-ttu-id="a2540-142">Die im Zuordnungsschema angegebenen Tabellen werden erstellt (die Datenbank muss vorhanden sein).</span><span class="sxs-lookup"><span data-stu-id="a2540-142">The tables that are identified in the mapping schema are created (the database must exist).</span></span> <span data-ttu-id="a2540-143">Wenn eine oder mehrere Tabellen bereits in der Datenbank vorhanden sind, bestimmt die SGDropTables-Eigenschaft, ob diese bereits vorhandenen Tabellen gelöscht und neu erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a2540-143">If one or more of the tables already exists in the database, the SGDropTables property determines whether these preexisting tables are to be dropped and re-created.</span></span>  
  
-   <span data-ttu-id="a2540-144">Wenn Sie die SchemaGen-Eigenschaft angeben (z. b. SchemaGen = true), werden die Tabellen erstellt, die im Mapping-Schema identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="a2540-144">If you specify the SchemaGen property (for example, SchemaGen = true), the tables that are identified in the mapping schema are created.</span></span> <span data-ttu-id="a2540-145">SchemaGen erstellt jedoch keine Einschränkungen (z. b. die PRIMARY KEY/FOREIGN KEY-Einschränkungen) für diese Tabellen mit einer Ausnahme: Wenn die XML-Knoten, die den Primärschlüssel in einer Beziehung bilden, als XML-Typ der ID definiert sind (d. h. `type="xsd:ID"` für XSD) und die SGUseID-Eigenschaft für SchemaGen auf true festgelegt ist, werden nicht nur Primärschlüssel aus den typisierten ID-Knoten erstellt, sondern es werden Primärschlüssel-/Fremdschlüssel Beziehungen aus Zuordnungsschema Beziehungen erstellt</span><span class="sxs-lookup"><span data-stu-id="a2540-145">But SchemaGen does not create any constraints (such as the PRIMARY KEY/FOREIGN KEY constraints) on these tables with one exception: If the XML nodes that constitute the primary key in a relationship are defined as having an XML type of ID (that is, `type="xsd:ID"` for XSD) AND the SGUseID property is set to True for SchemaGen, then not only are primary keys created from the ID typed nodes, but primary key/foreign key relationships are created from mapping schema relationships.</span></span>  
  
-   <span data-ttu-id="a2540-146">SchemaGen verwendet keine XSD-Schema Facetten und-Erweiterungen zum Generieren des relationalen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Schemas.</span><span class="sxs-lookup"><span data-stu-id="a2540-146">SchemaGen does not use XSD schema facets and extensions to generate the relational [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] schema.</span></span>  
  
-   <span data-ttu-id="a2540-147">Wenn Sie die SchemaGen-Eigenschaft (z. b. SchemaGen = true) beim Massen Laden angeben, werden nur die angegebenen Tabellen (und keine Sichten des freigegebenen namens) aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="a2540-147">If you specify the SchemaGen property (for example, SchemaGen = true) on Bulk Load, only tables (and not views of shared name) that are specified are updated.</span></span>  
  
-   <span data-ttu-id="a2540-148">SchemaGen stellt nur grundlegende Funktionen zum Erstellen des relationalen Schemas aus XSD mit Anmerkungen bereit.</span><span class="sxs-lookup"><span data-stu-id="a2540-148">SchemaGen only provides basic functionality for generating the relational schema from annotated XSD.</span></span> <span data-ttu-id="a2540-149">Der Benutzer muss die generierten Tabellen ggf. manuell ändern.</span><span class="sxs-lookup"><span data-stu-id="a2540-149">The user should modify the generated tables manually, if needed.</span></span>  
  
-   <span data-ttu-id="a2540-150">Wenn zwischen Tabellen mehr als eine Beziehung besteht, versucht SchemaGen, eine einzelne Beziehung zu erstellen, die alle Schlüssel enthält, die zwischen den beiden Tabellen beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="a2540-150">Where more than relationship exists between tables,SchemaGen tries to create a single relationship that includes all the keys involved between the two tables.</span></span> <span data-ttu-id="a2540-151">Diese Einschränkung kann die Ursache eines [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Fehlers sein.</span><span class="sxs-lookup"><span data-stu-id="a2540-151">This limitation might be the cause of a [!INCLUDE[tsql](../../../includes/tsql-md.md)] error.</span></span>  
  
-   <span data-ttu-id="a2540-152">Beim Massenladen von XML-Daten in eine Datenbank muss mindestens ein Attribut oder ein untergeordnetes Element im Zuordnungsschema vorhanden sein, das einer Datenbankspalte zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a2540-152">When you are bulk loading XML data into a database, there must be at least one attribute or child element in the mapping schema that is mapped to a database column.</span></span>  
  
-   <span data-ttu-id="a2540-153">Wenn Sie Datenwerte mithilfe von XML-Massenladen einfügen, müssen die Werte im Format (-)CCYY-MM-DD((+-)TZ) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a2540-153">If you are inserting date values by using XML Bulk Load, the values must be specified in the (-)CCYY-MM-DD((+-)TZ) format.</span></span> <span data-ttu-id="a2540-154">Dies ist das XSD-Standardformat für das Datum.</span><span class="sxs-lookup"><span data-stu-id="a2540-154">This is the standard XSD format for the date.</span></span>  
  
-   <span data-ttu-id="a2540-155">Einige Eigenschaftenflags sind mit anderen Eigenschaftenflags nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="a2540-155">Some property flags are not compatible with other property flags.</span></span> <span data-ttu-id="a2540-156">Beispielsweise wird beim Massenladen `Ignoreduplicatekeys=true` nicht gleichzeitig mit `Keepidentity=false` unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a2540-156">For example, bulk load does not support `Ignoreduplicatekeys=true` together with `Keepidentity=false`.</span></span> <span data-ttu-id="a2540-157">Bei `Keepidentity=false` wird für das Massenladen erwartet, dass der Server die Schlüsselwerte generiert.</span><span class="sxs-lookup"><span data-stu-id="a2540-157">When `Keepidentity=false`, bulk load expects the server to generate the key values.</span></span> <span data-ttu-id="a2540-158">Tabellen sollten für den Schlüssel eine `IDENTITY`-Einschränkung besitzen.</span><span class="sxs-lookup"><span data-stu-id="a2540-158">Tables should have an `IDENTITY` constraint on the key.</span></span> <span data-ttu-id="a2540-159">Der Server generiert keine doppelten Schlüssel, was bedeutet, dass `Ignoreduplicatekeys` nicht auf `true` festgelegt werden muss.</span><span class="sxs-lookup"><span data-stu-id="a2540-159">The server will not generate duplicate keys, which means there is no need for `Ignoreduplicatekeys` to be set to `true`.</span></span> <span data-ttu-id="a2540-160">`Ignoreduplicatekeys` muss nur dann auf `true` festgelegt werden, wenn Primärschlüsselwerte aus den eingehenden Daten in eine Tabelle mit Zeilen hochgeladen werden und es möglicherweise Konflikte im Zusammenhang mit Primärschlüsselwerten gibt.</span><span class="sxs-lookup"><span data-stu-id="a2540-160">`Ignoreduplicatekeys` should be set to `true` only when uploading primary key values from the incoming data into a table that has rows and there is a potential for conflict of primary key values.</span></span>  
  
  
