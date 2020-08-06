---
title: Explizite Zuordnung von XSD-Elementen und-Attributen zu Tabellen und Spalten (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit schema mapping [SQLXML]
- XPath queries [SQLXML], annotated XSD schemas in queries
- sql:field
- row mapping [SQLXML]
- attribute mapping [SQLXML], explicit mapping
- field annotation
- XSD schemas [SQLXML], mapping attributes and elements
- names [SQLXML]
- relation annotation
- table/view mapping [SQLXML], explicit mapping
- sql:relation
- mapping schema [SQLXML], explicit mapping
- annotated XSD schemas, mapping attributes and elements
- column mapping [SQLXML]
- element mapping [SQLXML], explicit mapping
- table mapping [SQLXML], explicit mapping
- element/attribute mapping [SQLXML]
ms.assetid: 7a5ebeb6-7322-4141-a307-ebcf95976146
author: rothja
ms.author: jroth
ms.openlocfilehash: f3400682b5f28835ca039912aab058691929a6c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609754"
---
# <a name="explicit-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-40"></a><span data-ttu-id="65797-102">Explizite Zuordnung von XSD-Elementen und -Attributen zu Tabellen und Spalten (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="65797-102">Explicit Mapping of XSD Elements and Attributes to Tables and Columns (SQLXML 4.0)</span></span>
  <span data-ttu-id="65797-103">Wenn ein XSD-Schema zur Bereitstellung einer XML-Sicht der relationalen Datenbank verwendet wird, müssen die Elemente und Attribute des Schemas den Tabellen und Spalten der Datenbank zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="65797-103">When using an XSD schema to provide an XML view of the relational database , the elements and attributes of the schema must be mapped to tables and columns of the database.</span></span> <span data-ttu-id="65797-104">Die Zeilen in der Datenbanktabelle/-sicht werden den Elementen im XML-Dokument zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="65797-104">The rows in the database table/view will map to elements in the XML document.</span></span> <span data-ttu-id="65797-105">Die Spaltenwerte in der Datenbank werden Attributen oder Elementen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="65797-105">The column values in the database map to attributes or elements.</span></span>  
  
 <span data-ttu-id="65797-106">Wenn Xpath-Abfragen für das mit Anmerkungen versehene XSD-Schema angegeben werden, werden die Daten für die Elemente und Attribute im Schema aus den Tabellen und Spalten abgerufen, denen sie zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="65797-106">When XPath queries are specified against the annotated XSD schema, the data for the elements and attributes in the schema is retrieved from the tables and columns to which they map.</span></span> <span data-ttu-id="65797-107">Um einen einzelnen Wert aus der Datenbank abrufen zu können, muss die im XSD-Schema angegebene Zuordnung sowohl über eine Beziehungs- als auch eine Feldangabe verfügen.</span><span class="sxs-lookup"><span data-stu-id="65797-107">To obtain a single value from the database, the mapping specified in the XSD schema must have both relation and field specification.</span></span> <span data-ttu-id="65797-108">Wenn der Name eines Elements/Attributs nicht mit dem Namen der zugeordneten Tabelle/Sicht oder Spalte identisch ist, werden die `sql:relation`-Anmerkung und die `sql:field`-Anmerkung verwendet, um die Zuordnung zwischen einem Element oder Attribut in einem XML-Dokument und der Tabelle (Sicht) oder Spalten in einer Datenbank anzugeben.</span><span class="sxs-lookup"><span data-stu-id="65797-108">If the name of an element/attribute is not the same name as the table/view or column name to which it maps, the `sql:relation` and `sql:field` annotations are used to specify the mapping between an element or attribute in an XML document and the table (view) or column in a database.</span></span>  
  
## <a name="sql-relation"></a><span data-ttu-id="65797-109">sql-Beziehung</span><span class="sxs-lookup"><span data-stu-id="65797-109">sql-relation</span></span>  
 <span data-ttu-id="65797-110">Die `sql:relation`-Anmerkung wird hinzugefügt, um einen XML-Knoten im XSD-Schema einer Datenbanktabelle zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="65797-110">The `sql:relation` annotation is added to map an XML node in the XSD schema to a database table.</span></span> <span data-ttu-id="65797-111">Der Name einer Tabelle (Sicht) wird als Wert der `sql:relation`-Anmerkung angegeben.</span><span class="sxs-lookup"><span data-stu-id="65797-111">The name of a table (view) is specified as the value of the `sql:relation` annotation.</span></span>  
  
 <span data-ttu-id="65797-112">Wenn `sql:relation` für ein Element angegeben wird, gilt der Bereich dieser Anmerkung für alle Attribute und untergeordneten Elemente, die in der komplexen Typdefinition des Elements beschrieben sind. Dadurch wird das Schreiben von Anmerkungen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="65797-112">When `sql:relation` is specified on an element, the scope of this annotation applies to all attributes and child elements that are described in the complex type definition of that element, therefore providing a shortcut in writing annotations.</span></span>  
  
 <span data-ttu-id="65797-113">Die-Anmerkung `sql:relation` ist auch nützlich, wenn Bezeichner, die in gültig sind, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in XML ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="65797-113">The `sql:relation` annotation is also useful when identifiers that are valid in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are not valid in XML.</span></span> <span data-ttu-id="65797-114">Zum Beispiel ist "Order Details" ein gültiger Tabellenname in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], jedoch nicht in XML.</span><span class="sxs-lookup"><span data-stu-id="65797-114">For example, "Order Details" is a valid table name in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but not in XML.</span></span> <span data-ttu-id="65797-115">In solchen Fällen kann die `sql:relation`-Anmerkung verwendet werden, um die Zuordnung anzugeben. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="65797-115">In such cases, the `sql:relation` annotation can be used to specify the mapping, for example:</span></span>  
  
```  
<xsd:element name="OD" sql:relation="[Order Details]">  
```  
  
## <a name="sql-field"></a><span data-ttu-id="65797-116">sql-Feld</span><span class="sxs-lookup"><span data-stu-id="65797-116">sql-field</span></span>  
 <span data-ttu-id="65797-117">Die `sql-field`-Anmerkung ordnet ein Element oder Attribut einer Datenbankspalte zu.</span><span class="sxs-lookup"><span data-stu-id="65797-117">The `sql-field` annotation maps an element or attribute to a database column.</span></span> <span data-ttu-id="65797-118">Die `sql:field`-Anmerkung wird hinzugefügt, um einen XML-Knoten im Schema einer Datenbankspalte zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="65797-118">The `sql:field` annotation is added to map an XML node in the schema to a database column.</span></span> <span data-ttu-id="65797-119">Sie können `sql:field` für ein Element ohne Inhalt angeben.</span><span class="sxs-lookup"><span data-stu-id="65797-119">You cannot specify `sql:field` on an empty content element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="65797-120">Beispiele</span><span class="sxs-lookup"><span data-stu-id="65797-120">Examples</span></span>  
 <span data-ttu-id="65797-121">Es müssen bestimmte Anforderungen erfüllt sein, damit aus den folgenden Beispielen funktionierende Beispiele erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="65797-121">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="65797-122">Weitere Informationen finden Sie unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="65797-122">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlrelation-and-sqlfield-annotations"></a><span data-ttu-id="65797-123">A.</span><span class="sxs-lookup"><span data-stu-id="65797-123">A.</span></span> <span data-ttu-id="65797-124">Angeben der Anmerkungen sql:relation und sql:field</span><span class="sxs-lookup"><span data-stu-id="65797-124">Specifying the sql:relation and sql:field annotations</span></span>  
 <span data-ttu-id="65797-125">In diesem Beispiel besteht das XSD-Schema aus einem **\<Contact>** Element des komplexen Typs mit **\<FName>** den untergeordneten **\<LName>** Elementen und und dem **ContactID** -Attribut.</span><span class="sxs-lookup"><span data-stu-id="65797-125">In this example, the XSD schema consists of an **\<Contact>** element of complex type with **\<FName>** and **\<LName>** child elements and the **ContactID** attribute.</span></span>  
  
 <span data-ttu-id="65797-126">Die-Anmerkung `sql:relation` ordnet das- **\<Contact>** Element der Person. Contact-Tabelle in der AdventureWorks-Datenbank zu.</span><span class="sxs-lookup"><span data-stu-id="65797-126">The `sql:relation` annotation maps the **\<Contact>** element to the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="65797-127">Die `sql:field` -Anmerkung ordnet das **\<FName>** -Element der FirstName-Spalte und das- **\<LName>** Element der LastName-Spalte zu.</span><span class="sxs-lookup"><span data-stu-id="65797-127">The `sql:field` annotation maps the **\<FName>** element to the FirstName column and the **\<LName>** element to the LastName column.</span></span>  
  
 <span data-ttu-id="65797-128">Für das **ContactID** -Attribut wird keine Anmerkung angegeben.</span><span class="sxs-lookup"><span data-stu-id="65797-128">No annotation is specified for the **ContactID** attribute.</span></span> <span data-ttu-id="65797-129">Dies führt zu einer Standardzuordnung des Attributs zur Spalte mit dem gleichen Namen.</span><span class="sxs-lookup"><span data-stu-id="65797-129">This results in a default mapping of the attribute to the column with the same name.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Contact" sql:relation="Person.Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"  
                     sql:field="FirstName"   
                     type="xsd:string" />   
        <xsd:element name="LName"    
                     sql:field="LastName"    
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ContactID"   
                       type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="65797-130">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="65797-130">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="65797-131">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="65797-131">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="65797-132">Speichern Sie die Datei unter dem Dateinamen MySchema-annotated.xml.</span><span class="sxs-lookup"><span data-stu-id="65797-132">Save the file as MySchema-annotated.xml.</span></span>  
  
2.  <span data-ttu-id="65797-133">Kopieren Sie die unten stehende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="65797-133">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="65797-134">Speichern Sie die Datei unter dem Namen MySchema-annotatedT.xml im gleichen Verzeichnis, in dem Sie MySchema-annotated.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="65797-134">Save the file as MySchema-annotatedT.xml in the same directory where you saved MySchema-annotated.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="MySchema-annotated.xml">  
        /Contact  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="65797-135">Der für das Zuordnungsschema (MySchema-annotated.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="65797-135">The directory path specified for the mapping schema (MySchema-annotated.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="65797-136">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="65797-136">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchema-annotated.xml"  
    ```  
  
3.  <span data-ttu-id="65797-137">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="65797-137">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="65797-138">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="65797-138">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="65797-139">Im Folgenden wird ein Teil des Resultsets aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="65797-139">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
 <Contact ContactID="1">   
    <FName>Gustavo</FName>   
    <LName>Achong</LName>   
 </Contact>   
  .....  
</ROOT>  
```  
  
  
