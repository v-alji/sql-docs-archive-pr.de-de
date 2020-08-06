---
title: Verwenden von XSD-Schemas mit Anmerkungen in Abfragen (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML]
- inline schemas [SQLXML]
- XPath queries [SQLXML], annotated XSD schemas in queries
- queries [SQLXML], annotated XSD schemas
- retrieving data
- mapping schema [SQLXML], queries
- multiple inline schemas
- annotated XSD schemas, queries
- XSD schemas [SQLXML], queries
- templates [SQLXML], annotated XSD schemas in queries
ms.assetid: 927a30a2-eae8-420d-851d-551c5f884f3c
author: rothja
ms.author: jroth
ms.openlocfilehash: c3038ea234f707da7a87a030cb4110510f5a77c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619723"
---
# <a name="using-annotated-xsd-schemas-in-queries-sqlxml-40"></a><span data-ttu-id="1bab7-102">Verwenden von XSD-Schemas mit Anmerkungen in Abfragen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="1bab7-102">Using Annotated XSD Schemas in Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="1bab7-103">Sie können Abfragen auf ein Schema mit Anmerkungen angeben, um Daten von der Datenbank abzurufen, indem Sie Xpath-Abfragen in einer Vorlage auf ein XSD-Schema festlegen.</span><span class="sxs-lookup"><span data-stu-id="1bab7-103">You can specify queries against an annotated schema to retrieve data from the database by specifying XPath queries in a template against the XSD schema.</span></span>  
  
 <span data-ttu-id="1bab7-104">Mit dem- **\<sql:xpath-query>** Element können Sie eine XPath-Abfrage für die XML-Sicht angeben, die durch das Schema mit Anmerkungen definiert wird.</span><span class="sxs-lookup"><span data-stu-id="1bab7-104">The **\<sql:xpath-query>** element allows you to specify an XPath query against the XML view that is defined by the annotated schema.</span></span> <span data-ttu-id="1bab7-105">Das mit Anmerkungen versehene Schema, für das die XPath-Abfrage ausgeführt werden soll, wird mithilfe des- `mapping-schema` Attributs des- **\<sql:xpath-query>** Elements identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1bab7-105">The annotated schema against which the XPath query is to be executed is identified by using the `mapping-schema` attribute of the **\<sql:xpath-query>** element.</span></span>  
  
 <span data-ttu-id="1bab7-106">Vorlagen sind gültige XML-Dokumente, die eine oder mehrere Abfragen enthalten.</span><span class="sxs-lookup"><span data-stu-id="1bab7-106">Templates are valid XML documents that contain one or more queries.</span></span> <span data-ttu-id="1bab7-107">Die FOR XML- und XPath-Abfragen geben ein Dokumentfragment zurück.</span><span class="sxs-lookup"><span data-stu-id="1bab7-107">The FOR XML and XPath queries return a document fragment.</span></span> <span data-ttu-id="1bab7-108">Vorlagen fungieren als Container für die Dokumentfragmente und bieten so eine Möglichkeit, ein einzelnes Element der obersten Ebene anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1bab7-108">Templates act as containers for the document fragments; templates thus provide a way to specify a single, top-level element.</span></span>  
  
 <span data-ttu-id="1bab7-109">In den Beispielen in diesem Thema werden Vorlagen dazu verwendet, eine XPath-Abfrage für ein Schema mit Anmerkungen auszuführen, um Daten von der Datenbank abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1bab7-109">The examples in this topic use templates to specify an XPath query against an annotated schema to retrieve data from the database.</span></span>  
  
 <span data-ttu-id="1bab7-110">Beachten Sie z. b. das Schema mit Anmerkungen:</span><span class="sxs-lookup"><span data-stu-id="1bab7-110">For example, consider this annotated schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID" type="xsd:string" />   
       <xsd:attribute name="FirstName" type="xsd:string" />   
       <xsd:attribute name="LastName"  type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="1bab7-111">Zur Veranschaulichung wird dieses XSD-Schema in einer Datei mit dem Namen Schema2.xml gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1bab7-111">For the purpose of illustration, this XSD schema is stored in file named Schema2.xml.</span></span> <span data-ttu-id="1bab7-112">Sie können dann eine Xpath-Abfrage auf das in der folgenden Vorlagendatei angegebene Schema mit Anmerkungen (Schema2.xml) ausführen:</span><span class="sxs-lookup"><span data-stu-id="1bab7-112">You could then have an XPath query against the annotated schema specified in the following template file (Schema2T.xml):</span></span>  
  
```  
<sql:xpath-query   
     xmlns:sql="urn:schemas-microsoft-com:xmlsql"  
     >  
          Person.Contact[@ContactID="1"]  
</sql:xpath-query>  
```  
  
 <span data-ttu-id="1bab7-113">Sie können dann das SQLXML 4.0-Testskript (Sqlxml4test.vbs) erstellen und es dazu verwenden, die Abfrage als Teil der Vorlagedatei auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1bab7-113">You can then create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the query as part of a template file.</span></span> <span data-ttu-id="1bab7-114">Weitere Informationen finden Sie unter [mit Anmerkungen versehene XDR-Schemas &#40;in SQLXML 4,0&#41;veraltet ](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="1bab7-114">For more information, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="using-inline-mapping-schemas"></a><span data-ttu-id="1bab7-115">Verwenden von Inlinezuordnungsschemas</span><span class="sxs-lookup"><span data-stu-id="1bab7-115">Using Inline Mapping Schemas</span></span>  
 <span data-ttu-id="1bab7-116">Ein Schema mit Anmerkungen kann direkt in eine Vorlage eingefügt werden, und dann kann eine Xpath-Abfrage in der Vorlage auf das Inlineschema angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1bab7-116">An annotated schema can be included directly in a template, and then an XPath query can be specified in the template against the inline schema.</span></span> <span data-ttu-id="1bab7-117">Die Vorlage kann auch ein Updategram sein.</span><span class="sxs-lookup"><span data-stu-id="1bab7-117">The template can also be an updategram.</span></span>  
  
 <span data-ttu-id="1bab7-118">Eine Vorlage kann mehrere Inlineschemas einschließen.</span><span class="sxs-lookup"><span data-stu-id="1bab7-118">A template can include multiple inline schemas.</span></span> <span data-ttu-id="1bab7-119">Wenn Sie ein Inline Schema verwenden möchten, das in einer Vorlage enthalten ist, geben Sie das **ID** -Attribut mit einem eindeutigen Wert für das **\<xsd:schema>** -Element an, und verwenden Sie dann **#idValue** , um auf das Inline Schema zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="1bab7-119">To use an inline schema that is included in a template, specify the **id** attribute with a unique value on the **\<xsd:schema>** element, and then use **#idvalue** to reference the inline schema.</span></span> <span data-ttu-id="1bab7-120">Das **ID** -Attribut ist identisch mit der **SQL: ID** ({urn: Schemas-Microsoft-com: XML-SQL}-ID), die in XDR-Schemas verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1bab7-120">The **id** attribute is identical in behavior to the **sql:id** ({urn:schemas-microsoft-com:xml-sql}id) used in XDR schemas.</span></span>  
  
 <span data-ttu-id="1bab7-121">Die folgende Vorlage gibt beispielsweise zwei Inlineschemas mit Anmerkungen an:</span><span class="sxs-lookup"><span data-stu-id="1bab7-121">For example, the following template specifies two inline-annotated schemas:</span></span>  
  
```  
<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'>  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
        xmlns:ms='urn:schemas-microsoft-com:mapping-schema'  
        id='InLineSchema1' sql:is-mapping-schema='1'>  
  <xsd:element name='Employees' ms:relation='HumanResources.Employee'>  
    <xsd:complexType>  
      <xsd:attribute name='LoginID'   
                     type='xsd:string'/>  
      <xsd:attribute name='Title'   
                     type='xsd:string'/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
        xmlns:ms='urn:schemas-microsoft-com:mapping-schema'  
        id='InLineSchema2' sql:is-mapping-schema='1'>  
  <xsd:element name='Contacts' ms:relation='Person.Contact'>  
    <xsd:complexType>  
  
      <xsd:attribute name='ContactID'   
                     type='xsd:string' />  
      <xsd:attribute name='FirstName'   
                     type='xsd:string' />  
      <xsd:attribute name='LastName'   
                     type='xsd:string' />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
  
<sql:xpath-query xmlns:sql='urn:schemas-microsoft-com:xml-sql'   
        mapping-schema='#InLineSchema1'>  
    /Employees[@LoginID='adventure-works\guy1']  
</sql:xpath-query>  
  
<sql:xpath-query xmlns:sql='urn:schemas-microsoft-com:xml-sql'   
        mapping-schema='#InLineSchema2'>  
    /Contacts[@ContactID='1']  
</sql:xpath-query>  
</ROOT>  
```  
  
 <span data-ttu-id="1bab7-122">Die Vorlage gibt auch zwei XPath-Abfragen an.</span><span class="sxs-lookup"><span data-stu-id="1bab7-122">The template also specifies two XPath queries.</span></span> <span data-ttu-id="1bab7-123">Jedes der- **\<xpath-query>** Elemente identifiziert das Zuordnungsschema eindeutig, indem das-Attribut angegeben wird `mapping-schema` .</span><span class="sxs-lookup"><span data-stu-id="1bab7-123">Each of the **\<xpath-query>** elements uniquely identifies the mapping schema by specifying the `mapping-schema` attribute.</span></span>  
  
 <span data-ttu-id="1bab7-124">Wenn Sie ein Inline Schema in der Vorlage angeben, muss die-Anmerkung `sql:is-mapping-schema` auch für das-Element angegeben werden **\<xsd:schema>** .</span><span class="sxs-lookup"><span data-stu-id="1bab7-124">When you specify an inline schema in the template, the `sql:is-mapping-schema` annotation must also be specified on the **\<xsd:schema>** element.</span></span> <span data-ttu-id="1bab7-125">Die `sql:is-mapping-schema`-Anmerkung akzeptiert einen booleschen Wert (0 =false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="1bab7-125">The `sql:is-mapping-schema` takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="1bab7-126">Ein Inline Schema mit **SQL: is-Mapping-Schema = "1"** wird als Inline Schema mit Anmerkungen behandelt und nicht im XML-Dokument zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1bab7-126">An inline schema with **sql:is-mapping-schema="1"** is treated as inline annotated schema and is not returned in the XML document.</span></span>  
  
 <span data-ttu-id="1bab7-127">Die `sql:is-mapping-schema`-Anmerkung gehört zum Vorlagennamespace `urn:schemas-microsoft-com:xml-sql`.</span><span class="sxs-lookup"><span data-stu-id="1bab7-127">The `sql:is-mapping-schema` annotation belongs to the template namespace `urn:schemas-microsoft-com:xml-sql`.</span></span>  
  
 <span data-ttu-id="1bab7-128">Speichern Sie zum Testen dieses Beispiels die Vorlage (InlineSchemaTemplate.xml) in einem lokalen Verzeichnis und erstellen und verwenden Sie dann das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1bab7-128">To test this example, save the template (InlineSchemaTemplate.xml) in a local directory and then create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="1bab7-129">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="1bab7-129">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="1bab7-130">Zusätzlich zum Angeben des- `mapping-schema` Attributs für das- **\<sql:xpath-query>** Element in einer Vorlage (wenn eine XPath-Abfrage vorhanden ist) oder für **\<updg:sync>** ein Element in einem Update Gram können Sie folgende Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="1bab7-130">In addition to specifying the `mapping-schema` attribute on the **\<sql:xpath-query>** element in a template (when there is an XPath query), or on **\<updg:sync>** element in an updategram, you can do the following:</span></span>  
  
-   <span data-ttu-id="1bab7-131">Geben Sie das- `mapping-schema` Attribut für das- **\<ROOT>** Element (globale Deklaration) in der Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="1bab7-131">Specify the `mapping-schema` attribute on the **\<ROOT>** element (global declaration) in the template.</span></span> <span data-ttu-id="1bab7-132">Dieses Zuordnungsschema wird dann zum Standardschema, das von allen Xpath- und Updategram-Knoten verwendet wird, die keine explizite `mapping-schema`-Anmerkung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1bab7-132">This mapping schema then becomes the default schema that will be used by all XPath and updategram nodes that have no explicit `mapping-schema` annotation.</span></span>  
  
-   <span data-ttu-id="1bab7-133">Geben Sie das `mapping schema`-Attribut mithilfe des `Command`-Objekts in ADO an.</span><span class="sxs-lookup"><span data-stu-id="1bab7-133">Specify the `mapping schema` attribute by using the ADO `Command` object.</span></span>  
  
 <span data-ttu-id="1bab7-134">Das- `mapping-schema` Attribut, das für das-Element oder das-Element angegeben wird, **\<xpath-query>** **\<updg:sync>** hat den höchsten Rang. das ADO- `Command` Objekt hat die niedrigste Priorität.</span><span class="sxs-lookup"><span data-stu-id="1bab7-134">The `mapping-schema` attribute that is specified on the **\<xpath-query>** or **\<updg:sync>** element has the highest precedence; the ADO `Command` object has the lowest precedence.</span></span>  
  
 <span data-ttu-id="1bab7-135">Beachten Sie Folgendes: Wenn Sie eine XPath-Abfrage in einer Vorlage angeben und kein Zuordnungsschema angeben, für das die XPath-Abfrage ausgeführt wird, wird die XPath-Abfrage als eine **dbobject** -typabfrage behandelt.</span><span class="sxs-lookup"><span data-stu-id="1bab7-135">Note that if you specify an XPath query in a template and do not specify a mapping schema against which the XPath query is executed, the XPath query is treated as a **dbobject** type query.</span></span> <span data-ttu-id="1bab7-136">Betrachten Sie z. B. die folgende Vorlage:</span><span class="sxs-lookup"><span data-stu-id="1bab7-136">For example, consider this template:</span></span>  
  
```  
<sql:xpath-query   
     xmlns:sql="urn:schemas-microsoft-com:xmlsql">  
          Production.ProductPhoto[@ProductPhotoID='100']/@LargePhoto  
</sql:xpath-query>  
```  
  
 <span data-ttu-id="1bab7-137">Die Vorlage gibt eine XPath-Abfrage, aber kein Zuordnungsschema an.</span><span class="sxs-lookup"><span data-stu-id="1bab7-137">The template specifies an XPath query but it does not specify a mapping schema.</span></span> <span data-ttu-id="1bab7-138">Daher wird diese Abfrage als eine **dbobject** -typabfrage behandelt, bei der Production. ProductPhoto der Tabellenname und @ProductPhotoID = ' 100 ' ein Prädikat ist, das ein Produktfoto mit dem ID-Wert 100 findet.</span><span class="sxs-lookup"><span data-stu-id="1bab7-138">Therefore, this query is treated as a **dbobject** type query in which Production.ProductPhoto is the table name and @ProductPhotoID='100' is a predicate that finds a product photo with the ID value of 100.</span></span> <span data-ttu-id="1bab7-139">@LargePhotodie Spalte, aus der der Wert abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="1bab7-139">@LargePhoto is the column from which to retrieve the value.</span></span>  
  
  
