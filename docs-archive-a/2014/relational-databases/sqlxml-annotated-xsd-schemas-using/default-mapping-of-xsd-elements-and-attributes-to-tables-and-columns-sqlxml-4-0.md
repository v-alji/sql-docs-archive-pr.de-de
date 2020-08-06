---
title: Standard Zuordnung von XSD-Elementen und-Attributen zu Tabellen und Spalten (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XSD schemas [SQLXML], mapping attributes and elements
- mapping schema [SQLXML], default mapping
- element mapping [SQLXML], default mapping
- element mapping [SQLXML]
- table mapping [SQLXML]
- annotated XSD schemas, mapping attributes and elements
- table/view mapping [SQLXML]
- column mapping [SQLXML]
- attribute mapping [SQLXML], default mapping
- default schema mapping
- table mapping [SQLXML], default mapping
- testing XPath query against schema
- xml data type [SQL Server], SQLXML
- table/view mapping [SQLXML], default mapping
- element/attribute mapping [SQLXML]
ms.assetid: 9a18e92a-6cfb-4a14-993a-663a95aabb63
author: rothja
ms.author: jroth
ms.openlocfilehash: 0bccec2413e8a0a6e13283a0f3e5f63ab61e934b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617900"
---
# <a name="default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-40"></a><span data-ttu-id="c5ab4-102">Standardzuordnung von XSD-Elementen und -Attributen zu Tabellen und Spalten (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="c5ab4-102">Default Mapping of XSD Elements and Attributes to Tables and Columns (SQLXML 4.0)</span></span>
  <span data-ttu-id="c5ab4-103">Standardmäßig wird ein Element des komplexen Typs in einem mit Anmerkungen versehenen XSD-Schema der Tabelle (Sicht) mit dem gleichen Namen in der angegebenen Datenbank zugeordnet, und ein Element oder Attribut des einfachen Typs wird der Spalte mit demselben Namen in der Tabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-103">By default, an element of complex type in an XSD annotated schema maps to the table (view) with the same name in the specified database, and an element or attribute of simple type maps to the column with the same name in the table.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c5ab4-104">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c5ab4-104">Examples</span></span>  
 <span data-ttu-id="c5ab4-105">Es müssen bestimmte Anforderungen erfüllt sein, damit aus den folgenden Beispielen funktionierende Beispiele erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-105">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="c5ab4-106">Weitere Informationen finden Sie unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="c5ab4-106">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-default-mapping"></a><span data-ttu-id="c5ab4-107">A.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-107">A.</span></span> <span data-ttu-id="c5ab4-108">Angeben der Standardzuordnung</span><span class="sxs-lookup"><span data-stu-id="c5ab4-108">Specifying default mapping</span></span>  
 <span data-ttu-id="c5ab4-109">In diesem Beispiel werden keine Anmerkungen im XSD-Schema angegeben.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-109">In this example, no annotations are specified in the XSD schema.</span></span> <span data-ttu-id="c5ab4-110">Das **\<Person.Contact>** -Element weist einen komplexen Typ auf und wird daher standardmäßig der Person. Contact-Tabelle in der AdventureWorks-Datenbank zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-110">The **\<Person.Contact>** element is of complex type and, therefore, maps by default to the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="c5ab4-111">Alle Attribute (ContactID, FirstName, LastName) des-Elements weisen einen **\<Person.Contact>** einfachen Typ auf und werden standardmäßig Spalten mit denselben Namen in der Person. Contact-Tabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-111">All the attributes (ContactID, FirstName, LastName) of the **\<Person.Contact>** element are of simple type and map by default to columns with the same names in the Person.Contact table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID"  type="xsd:string" />   
       <xsd:attribute name="FirstName"   type="xsd:string" />   
       <xsd:attribute name="LastName"    type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="c5ab4-112">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="c5ab4-112">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="c5ab4-113">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-113">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="c5ab4-114">Speichern Sie die Datei unter dem Dateinamen MySchema.xml.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-114">Save the file as MySchema.xml.</span></span>  
  
2.  <span data-ttu-id="c5ab4-115">Kopieren Sie die folgende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-115">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="c5ab4-116">Speichern Sie die Datei unter dem Namen MySchemaT im gleichen Verzeichnis, in dem Sie MySchema.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-116">Save the file as MySchemaT.xml in the same directory where you saved MySchema.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchema.xml">  
            /Person.Contact  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="c5ab4-117">Der für das Zuordnungsschema (MySchema.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-117">The directory path specified for the mapping schema (MySchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="c5ab4-118">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c5ab4-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchema.xml"  
    ```  
  
3.  <span data-ttu-id="c5ab4-119">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="c5ab4-120">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c5ab4-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="c5ab4-121">Im Folgenden wird ein Teil des Resultsets aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c5ab4-121">Here is the partial result set:</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8" ?>  
<ROOT>  
  <Person.Contact ContactID="1" FirstName="Gustavo" LastName="Achong"/>  
  <Person.Contact ContactID="2" FirstName="Catherine" LastName="Abel"/>  
   ...  
</ROOT>  
```  
  
### <a name="b-mapping-an-xml-element-to-a-database-column"></a><span data-ttu-id="c5ab4-122">B.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-122">B.</span></span> <span data-ttu-id="c5ab4-123">Zuordnen eines XML-Elements zu einer Datenbankspalte</span><span class="sxs-lookup"><span data-stu-id="c5ab4-123">Mapping an XML element to a database column</span></span>  
 <span data-ttu-id="c5ab4-124">In diesem Beispiel findet die Standardzuordnung auch statt, da keine Anmerkungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-124">In this example, default mapping also takes place because no annotations are used.</span></span> <span data-ttu-id="c5ab4-125">Das **\<Person.Contact>** -Element weist einen komplexen Typ auf und wird der Tabelle mit demselben Namen in der Datenbank zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-125">The **\<Person.Contact>** element is of complex type and maps to the table with the same name in the database.</span></span> <span data-ttu-id="c5ab4-126">Die Elemente **\<FirstName>** und und das Mitarbeiter-ID- **\<LastName>** Attribut sind vom einfachen Typ und werden daher den gleichnamigen Spalten zugeordnet. **EmployeeID**</span><span class="sxs-lookup"><span data-stu-id="c5ab4-126">The elements **\<FirstName>** and **\<LastName>** and the **EmployeeID** attribute are of simple type and, therefore, map to the columns with the same names.</span></span> <span data-ttu-id="c5ab4-127">Der einzige Unterschied zwischen diesem und dem vorherigen Beispiel besteht darin, dass für die Zuordnung der Felder FirstName und LastName Elemente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-127">The only difference between this and the previous example are that elements are used for mapping the FirstName and LastName fields.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="FirstName" type="xsd:string" />   
        <xsd:element name="LastName" type="xsd:string" />   
      </xsd:sequence>  
      <xsd:attribute name="ContactID" type="xsd:integer" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="c5ab4-128">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="c5ab4-128">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="c5ab4-129">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-129">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="c5ab4-130">Speichern Sie die Datei unter dem Dateinamen MySchemaElements.xml.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-130">Save the file as MySchemaElements.xml.</span></span>  
  
2.  <span data-ttu-id="c5ab4-131">Erstellen Sie die folgende Vorlage (MySchemaElementsT.xml), und speichern Sie sie im gleichen Verzeichnis wie im vorherigen Schritt.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-131">Create the following template (MySchemaElementsT.xml), and save it in the same directory used in the previous step.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchemaElements.xml">  
            /Person.Contact  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="c5ab4-132">Der für das Zuordnungsschema angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-132">The directory path specified for the mapping schema is relative to the directory where the template is saved.</span></span> <span data-ttu-id="c5ab4-133">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c5ab4-133">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchemaElements.xml"  
    ```  
  
3.  <span data-ttu-id="c5ab4-134">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-134">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="c5ab4-135">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c5ab4-135">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="c5ab4-136">Im Folgenden wird ein Teil des Resultsets aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c5ab4-136">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact ContactID="1">  
    <FirstName>Gustavo</FirstName>  
    <LastName>Achong</LastName>  
  </Person.Contact>  
   ...  
</ROOT>  
```  
  
### <a name="c-mapping-an-xml-element-to-an-xml-data-type-column"></a><span data-ttu-id="c5ab4-137">C.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-137">C.</span></span> <span data-ttu-id="c5ab4-138">Zuordnen eines XML-Elements zu einer XML-Datentypspalte</span><span class="sxs-lookup"><span data-stu-id="c5ab4-138">Mapping an XML element to an XML data type column</span></span>  
 <span data-ttu-id="c5ab4-139">In diesem Beispiel findet die Standardzuordnung auch statt, da keine Anmerkungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-139">In this example, default mapping also takes place because no annotations are used.</span></span> <span data-ttu-id="c5ab4-140">Das **\<Production.ProductModel>** -Element weist einen komplexen Typ auf und wird der Tabelle mit demselben Namen in der Datenbank zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-140">The **\<Production.ProductModel>** element is of complex type and maps to the table with the same name in the database.</span></span> <span data-ttu-id="c5ab4-141">Das **ProductModelID** -Attribut ist vom einfachen Typ und wird daher den gleichnamigen Spalten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-141">The **ProductModelID** attribute is of simple type and, therefore, map to the columns with the same names.</span></span> <span data-ttu-id="c5ab4-142">Der einzige Unterschied zwischen diesem und den vorherigen Beispielen besteht darin, dass das- **\<Instructions>** Element einer Spalte entspricht, die den- `xml` Datentyp mithilfe des- `xsd:anyType` Typs verwendet.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-142">The only difference between this and the previous examples is that the **\<Instructions>** element is mapping to a column that uses the `xml` data type by using the `xsd:anyType` type.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Production.ProductModel">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Instructions" type="xsd:anyType" />   
      </xsd:sequence>  
      <xsd:attribute name="ProductModelID" type="xsd:integer" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="c5ab4-143">Der `xml`-Datentyp wurde in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-143">The `xml` data type was introduced in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="c5ab4-144">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="c5ab4-144">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="c5ab4-145">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-145">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="c5ab4-146">Speichern Sie die Datei unter dem Dateinamen MySchemaXmlAnyElements.xml.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-146">Save the file as MySchemaXmlAnyElements.xml.</span></span>  
  
2.  <span data-ttu-id="c5ab4-147">Erstellen Sie die folgende Vorlage (MySchemaXmlAnyElementsT.xml), und speichern Sie sie im gleichen Verzeichnis wie im vorherigen Schritt.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-147">Create the following template (MySchemaXmlAnyElementsT.xml), and save it in the same directory used in the previous step.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchemaXmlAnyElements.xml">  
            /Production.ProductModel[@ProductModelID=7]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="c5ab4-148">Der für das Zuordnungsschema angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-148">The directory path specified for the mapping schema is relative to the directory where the template is saved.</span></span> <span data-ttu-id="c5ab4-149">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c5ab4-149">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchemaXmlAnyElements.xml"  
    ```  
  
3.  <span data-ttu-id="c5ab4-150">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c5ab4-150">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="c5ab4-151">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c5ab4-151">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="c5ab4-152">Im Folgenden wird ein Teil des Resultsets aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c5ab4-152">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductModel ProductModelID="7">  
    <Instructions>  
      <root xmlns="http:  
//schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstru  
ctions">  
...  
      </root>  
    <Instructions>  
  </Production.ProductModel>  
</ROOT>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5ab4-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5ab4-153">See Also</span></span>  
 <span data-ttu-id="c5ab4-154">[Überlegungen zur Schema Sicherheit mit Anmerkungen &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="c5ab4-154">[Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="c5ab4-155">[XML-Daten &#40;SQL Server&#41;](../xml/xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c5ab4-155">[XML Data &#40;SQL Server&#41;](../xml/xml-data-sql-server.md) </span></span>  
 [<span data-ttu-id="c5ab4-156">XML-Datentypunterstützung für SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="c5ab4-156">xml Data Type Support in SQLXML 4.0</span></span>](../sqlxml/xml-data-type-support-in-sqlxml-4-0.md)  
  
  
