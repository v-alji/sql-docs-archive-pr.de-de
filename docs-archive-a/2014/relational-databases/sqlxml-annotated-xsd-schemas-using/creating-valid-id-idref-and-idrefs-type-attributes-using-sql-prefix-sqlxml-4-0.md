---
title: "Erstellen gültiger Attribute vom Typ ID, IDREF und IDREFS mit ' SQL: Prefix ' (SQLXML 4,0) | Microsoft-Dokumentation"
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREFS relationships [SQLXML]
- annotated XSD schemas, ID type attribute
- IDREF type attribute [SQLXML]
- annotated XSD schemas, IDREFS type attribute
- ID type attribute [SQLXML]
- sql:prefix
- prefix annotation
- IDREF relationships [SQLXML]
- IDREFS type attribute [SQLXML]
- annotated XSD schemas, IDREF type attribute
- ID relationships [SQLXML]
ms.assetid: 1c7f77d3-81f3-4820-bb63-c4aaa4ea9aa1
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9e63bebd0cebbfeed75ea5cbe2ea62683234fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617902"
---
# <a name="creating-valid-id-idref-and-idrefs-type-attributes-using-sqlprefix-sqlxml-40"></a><span data-ttu-id="188cd-102">Erstellen gültiger Attribute vom Typ ID, IDREF und IDREFS mit 'sql:prefix' (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="188cd-102">Creating Valid ID, IDREF, and IDREFS Type Attributes Using sql:prefix (SQLXML 4.0)</span></span>
  <span data-ttu-id="188cd-103">Für ein Attribut kann der ID-Attributtyp angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="188cd-103">An attribute can be specified to be an ID type attribute.</span></span> <span data-ttu-id="188cd-104">Attribute vom Typ IDREF oder IDRES können dann verwendet werden, um auf das ID-Attribut zu verweisen. Auf diese Weise werden Links zwischen Dokumenten gebildet.</span><span class="sxs-lookup"><span data-stu-id="188cd-104">Attributes specified as IDREF or IDREFS can then be used to refer to the ID type attributes, enabling links between documents.</span></span>  
  
 <span data-ttu-id="188cd-105">ID, IDREF und IDREFS entsprechen, abgesehen von wenigen Unterschieden, Primärschlüssel/Fremdschlüssel-Beziehungen in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="188cd-105">ID, IDREF, and IDREFS correspond to PK/FK (primary key/foreign key) relationships in the database, with few differences.</span></span> <span data-ttu-id="188cd-106">In einem XML-Dokument müssen die Werte von ID-Typattributen eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="188cd-106">In an XML document, the values of ID type attributes must be distinct.</span></span> <span data-ttu-id="188cd-107">Wenn **CustomerID** -und **OrderID** -Attribute als ID-Typ in einem XML-Dokument angegeben werden, müssen diese Werte unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="188cd-107">If **CustomerID** and **OrderID** attributes are specified as ID type in an XML document, these values must be distinct.</span></span> <span data-ttu-id="188cd-108">In einer Datenbank können die Spalten CustomerID und SalesOrderID allerdings die gleichen Werte haben.</span><span class="sxs-lookup"><span data-stu-id="188cd-108">However, in a database, CustomerID and OrderID columns can have the same values.</span></span> <span data-ttu-id="188cd-109">(Zum Beispiel sind die Einträge CustomerID = 1 und OrderID = 1 in der Datenbank gültig).</span><span class="sxs-lookup"><span data-stu-id="188cd-109">(For example, CustomerID = 1 and OrderID = 1 are valid in the database).</span></span>  
  
 <span data-ttu-id="188cd-110">Für die Gültigkeit der Attribute ID, IDREF und IDREFS gelten folgende Voraussetzungen:</span><span class="sxs-lookup"><span data-stu-id="188cd-110">For the ID, IDREF, and IDREFS attributes to be valid:</span></span>  
  
-   <span data-ttu-id="188cd-111">Der Wert von ID muss innerhalb des XML-Dokuments eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="188cd-111">The value of ID must be unique within the XML document.</span></span>  
  
-   <span data-ttu-id="188cd-112">Die ID-Werte, auf die jeweils in IDREF und IDREFS verwiesen wird, müssen im XML-Dokument enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="188cd-112">For every IDREF and IDREFS, the referenced ID values must be in the XML document.</span></span>  
  
-   <span data-ttu-id="188cd-113">Der Wert eines Attributs vom Typ ID, IDREF und IDREFS muss ein benanntes Token sein.</span><span class="sxs-lookup"><span data-stu-id="188cd-113">The value of an ID, IDREF, and IDREFS must be a named token.</span></span> <span data-ttu-id="188cd-114">(Beispielsweise kann der ganzzahlige Wert 101 kein ID-Wert sein.)</span><span class="sxs-lookup"><span data-stu-id="188cd-114">(For example, the integer value 101 cannot be an ID value.)</span></span>  
  
-   <span data-ttu-id="188cd-115">Die Attribute vom Typ ID, IDREF und IDREFS können keinen Spalten vom Typ `text`, `ntext` oder `image` bzw. einem anderen binären Datentyp (z. B. `timestamp`) zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="188cd-115">The attributes of ID, IDREF, and IDREFS type cannot be mapped to columns of the type `text`, `ntext`, or `image` or any other binary data type (for example, `timestamp`).</span></span>  
  
 <span data-ttu-id="188cd-116">Enthält ein XML-Dokument mehrere IDs, geben Sie die `sql:prefix`-Anmerkung an, um eindeutige Werte zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="188cd-116">If an XML document contains multiple IDs, use the `sql:prefix` annotation to ensure that the values are unique.</span></span>  
  
 <span data-ttu-id="188cd-117">Beachten Sie, dass die `sql:prefix`-Anmerkung nicht mit dem XSD-Attribut fixed verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="188cd-117">Note that `sql:prefix` annotation cannot be used with XSD fixed attribute.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="188cd-118">Beispiele</span><span class="sxs-lookup"><span data-stu-id="188cd-118">Examples</span></span>  
 <span data-ttu-id="188cd-119">Es müssen bestimmte Anforderungen erfüllt sein, damit aus den folgenden Beispielen funktionierende Beispiele erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="188cd-119">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="188cd-120">Weitere Informationen finden Sie unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="188cd-120">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-id-and-idrefs-types"></a><span data-ttu-id="188cd-121">A.</span><span class="sxs-lookup"><span data-stu-id="188cd-121">A.</span></span> <span data-ttu-id="188cd-122">Angeben von ID- und IDREFS-Typen</span><span class="sxs-lookup"><span data-stu-id="188cd-122">Specifying ID and IDREFS types</span></span>  
 <span data-ttu-id="188cd-123">Im folgenden Schema besteht das-Element aus dem untergeordneten- **\<Customer>** **\<Order>** Element.</span><span class="sxs-lookup"><span data-stu-id="188cd-123">In the following schema, the **\<Customer>** element consists of the **\<Order>** child element.</span></span> <span data-ttu-id="188cd-124">Das-Element **\<Order>** verfügt auch über ein untergeordnetes-Element, das- **\<OrderDetail>** Element.</span><span class="sxs-lookup"><span data-stu-id="188cd-124">The **\<Order>** element also has a child element, the **\<OrderDetail>** element.</span></span>  
  
 <span data-ttu-id="188cd-125">Das **OrderIDList** -Attribut von **\<Customer>** ist ein Attribut vom Typ IDREFS, das auf das **OrderID** -Attribut des- **\<Order>** Elements verweist.</span><span class="sxs-lookup"><span data-stu-id="188cd-125">The **OrderIDList** attribute of **\<Customer>** is an IDREFS type attribute that refers to the **OrderID** attribute of the **\<Order>** element.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
                 parent="Sales.Customer"  
                 parent-key="CustomerID"  
                 child="Sales.SalesOrderHeader"  
                 child-key="CustomerID" />  
    <sql:relationship name="OrderOrderDetail"  
                 parent="Sales.SalesOrderHeader"  
                 parent-key="SalesOrderID"  
                 child="Sales.SalesOrderDetail"  
                 child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"    
               sql:relationship="CustOrders" maxOccurs="unbounded" >  
          <xsd:complexType>  
              <xsd:sequence>  
                <xsd:element name="OrderDetail"   
                             sql:relation="Sales.SalesOrderDetail"   
                   sql:relationship="OrderOrderDetail"   
                   maxOccurs="unbounded" >  
                  <xsd:complexType>  
                   <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                   <xsd:attribute name="ProductID" type="xsd:string" />  
                   <xsd:attribute name="OrderQty" type="xsd:integer" />  
                  </xsd:complexType>  
               </xsd:element>  
             </xsd:sequence>  
             <xsd:attribute name="SalesOrderID"   
                            type="xsd:ID" sql:prefix="ord-" />  
             <xsd:attribute name="OrderDate" type="xsd:date" />  
             <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
      </xsd:element>  
    </xsd:sequence>  
    <xsd:attribute name="CustomerID" type="xsd:string" />  
    <xsd:attribute name="OrderIDList" type="xsd:IDREFS"   
                   sql:relation="Sales.SalesOrderHeader" sql:field="SalesOrderID"  
                   sql:relationship="CustOrders" sql:prefix="ord-">  
    </xsd:attribute>  
  </xsd:complexType>  
</xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="188cd-126">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="188cd-126">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="188cd-127">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="188cd-127">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="188cd-128">Speichern Sie die Datei unter dem Dateinamen sqlPrefix.xml.</span><span class="sxs-lookup"><span data-stu-id="188cd-128">Save the file as sqlPrefix.xml.</span></span>  
  
2.  <span data-ttu-id="188cd-129">Kopieren Sie die folgende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="188cd-129">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="188cd-130">Speichern Sie die Datei unter dem Dateinamen sqlPrefixT.xml im gleichen Verzeichnis wie sqlPrefix.xml.</span><span class="sxs-lookup"><span data-stu-id="188cd-130">Save the file as sqlPrefixT.xml in the same directory where you saved sqlPrefix.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="sqlPrefix.xml">  
        /Customer[@CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="188cd-131">Der für das Zuordnungsschema (sqlPrefix.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="188cd-131">The directory path specified for the mapping schema (sqlPrefix.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="188cd-132">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="188cd-132">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\sqlPrefix.xml"  
    ```  
  
3.  <span data-ttu-id="188cd-133">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="188cd-133">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="188cd-134">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="188cd-134">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="188cd-135">Dies ist das Teilergebnis:</span><span class="sxs-lookup"><span data-stu-id="188cd-135">This is the partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" OrderIDList="ord-43860 ord-44501 ord-45283 ord-46042">  
    <Order SalesOrderID="ord-43860" OrderDate="2001-08-01" CustomerID="1">  
      <OrderDetail SalesOrderID="43860" ProductID="729" OrderQty="1" />   
      <OrderDetail SalesOrderID="43860" ProductID="732" OrderQty="1" />   
      <OrderDetail SalesOrderID="43860" ProductID="738" OrderQty="1" />   
      <OrderDetail SalesOrderID="43860" ProductID="753" OrderQty="2" />   
      ...  
    </Order>  
    ...  
 </Customer>  
</ROOT>  
```  
  
  
