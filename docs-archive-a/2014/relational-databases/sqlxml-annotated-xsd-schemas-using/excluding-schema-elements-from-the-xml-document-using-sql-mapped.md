---
title: 'Ausschließen von Schema Elementen aus dem resultierenden XML-Dokument mithilfe von SQL: zugeordnet (SQLXML 4,0) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- element does not map [SQLXML]
- annotated XSD schemas, excluding schema elements
- mapped annotation
- table mapping [SQLXML], excluding schema elements
- sql:mapped
- excluding schema elements
- element mapping [SQLXML], excluding schema elements
- column mapping [SQLXML]
- XSD schemas [SQLXML], excluding schema elements
- attribute mapping [SQLXML], excluding schema elements
- table/view mapping [SQLXML], excluding schema elements
ms.assetid: 7d2649dd-0038-4a2c-b16d-f80f7c306966
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c79ae005b9630fcbfcd16bfc22c2aeb21b7bf9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617901"
---
# <a name="excluding-schema-elements-from-the-resulting-xml-document-using-sqlmapped-sqlxml-40"></a><span data-ttu-id="c8755-102">Ausschließen von Schemaelementen aus dem resultierenden XML-Dokument mithilfe von 'sql:mapped' (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="c8755-102">Excluding Schema Elements from the Resulting XML Document Using sql:mapped (SQLXML 4.0)</span></span>
  <span data-ttu-id="c8755-103">Aufgrund der Standardzuordnung werden alle Elemente und Attribute im XSD-Schema einer Datenbanktabelle/-sicht und -spalte zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c8755-103">Every element and attribute in the XSD schema maps to a database table/view and column because of the default mapping.</span></span> <span data-ttu-id="c8755-104">Wenn Sie ein Element im XDR-Schema erstellen möchten, das keiner Datenbanktabelle (Sicht) oder -spalte zugeordnet und im XML-Dokument nicht angezeigt wird, können Sie die `sql:mapped`-Anmerkung angeben.</span><span class="sxs-lookup"><span data-stu-id="c8755-104">If you want to create an element in the XSD schema that does not map to any database table (view) or column and that does not appear in the XML, you can specify the `sql:mapped` annotation.</span></span>  
  
 <span data-ttu-id="c8755-105">Die `sql:mapped`-Anmerkung ist besonders hilfreich, wenn das Schema nicht geändert werden kann oder verwendet wird, um XML aus anderen Quellen zu überprüfen, und außerdem Daten enthält, die nicht in der Datenbank gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c8755-105">The `sql:mapped` annotation is especially useful if the schema cannot be modified or if the schema is used to validate XML from other sources and yet contains data that is not stored in your database.</span></span> <span data-ttu-id="c8755-106">Die `sql:mapped`-Anmerkung unterscheidet sich von der `sql:is-constant`-Anmerkung insofern, als dass die nicht zugeordneten Elemente und Attribute nicht im XML-Dokument angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c8755-106">The `sql:mapped` annotation differs from `sql:is-constant` in that the unmapped elements and attributes do not appear in the XML document.</span></span>  
  
 <span data-ttu-id="c8755-107">Die `sql:mapped`-Anmerkung akzeptiert einen booleschen Wert (0 = false und 1 = true).</span><span class="sxs-lookup"><span data-stu-id="c8755-107">The `sql:mapped` annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="c8755-108">Zulässig sind die Werte 0, 1, true und false.</span><span class="sxs-lookup"><span data-stu-id="c8755-108">The acceptable values are 0, 1, true, and false.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c8755-109">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c8755-109">Examples</span></span>  
 <span data-ttu-id="c8755-110">Es müssen bestimmte Anforderungen erfüllt sein, damit aus den folgenden Beispielen funktionierende Beispiele erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="c8755-110">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="c8755-111">Weitere Informationen finden Sie unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="c8755-111">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlmapped-annotation"></a><span data-ttu-id="c8755-112">A.</span><span class="sxs-lookup"><span data-stu-id="c8755-112">A.</span></span> <span data-ttu-id="c8755-113">Angeben der "sql:mapped"-Anmerkung</span><span class="sxs-lookup"><span data-stu-id="c8755-113">Specifying the sql:mapped annotation</span></span>  
 <span data-ttu-id="c8755-114">Angenommen, Sie haben ein XSD-Schema von einer anderen Quelle.</span><span class="sxs-lookup"><span data-stu-id="c8755-114">Assume you have an XSD schema from some other source.</span></span> <span data-ttu-id="c8755-115">Dieses XSD-Schema besteht aus einem- **\<Person.Contact>** Element mit den Attributen **ContactID**, **FirstName**, **LastName**und **HomeAddress** .</span><span class="sxs-lookup"><span data-stu-id="c8755-115">This XSD schema consists of an **\<Person.Contact>** element with **ContactID**, **FirstName**, **LastName**, and **HomeAddress** attributes.</span></span>  
  
 <span data-ttu-id="c8755-116">Beim Zuordnen dieses XSD-Schemas zur Person. Contact-Tabelle in der AdventureWorks-Datenbank `sql:mapped` wird im **HomeAddress** -Attribut angegeben, da in der Employees-Tabelle nicht die Privatadressen von Mitarbeitern gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c8755-116">In mapping this XSD schema to the Person.Contact table in the AdventureWorks database, `sql:mapped` is specified on the **HomeAddress** attribute because the Employees table does not store the home addresses of employees.</span></span> <span data-ttu-id="c8755-117">Daher wird dieses Attribut nicht der Datenbank zugeordnet und nicht im resultierenden XML-Dokument zurückgegeben, wenn eine XPath-Abfrage mit dem Zuordnungsschema ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c8755-117">As a result, this attribute is not mapped to the database and is not returned in the resulting XML document when an XPath query is specified against the mapping schema.</span></span>  
  
 <span data-ttu-id="c8755-118">Für den Rest des Schemas wird eine Standardzuordnung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="c8755-118">Default mapping takes place for the rest of the schema.</span></span> <span data-ttu-id="c8755-119">Das **\<Person.Contact>** -Element wird der Person. Contact-Tabelle zugeordnet, und alle Attribute werden den gleichnamigen Spalten in der Person. Contact-Tabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c8755-119">The **\<Person.Contact>** element maps to the Person.Contact table, and all the attributes map to the columns with the same name in the Person.Contact table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact">  
    <xsd:complexType>  
      <xsd:attribute name="ContactID"   type="xsd:string"/>  
      <xsd:attribute name="FirstName"    type="xsd:string" />  
      <xsd:attribute name="LastName"     type="xsd:string" />  
      <xsd:attribute name="HomeAddress" type="xsd:string"   
                     sql:mapped="false" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="c8755-120">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="c8755-120">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="c8755-121">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="c8755-121">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="c8755-122">Speichern Sie die Datei unter dem Dateinamen sql-mapped.xml.</span><span class="sxs-lookup"><span data-stu-id="c8755-122">Save the file as sql-mapped.xml.</span></span>  
  
2.  <span data-ttu-id="c8755-123">Kopieren Sie die folgende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="c8755-123">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="c8755-124">Speichern Sie die Datei unter dem Namen sql-mappedT.xml im gleichen Verzeichnis, in dem Sie sql-mapped.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="c8755-124">Save the file as sql-mappedT.xml in the same directory where you saved sql-mapped.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sql-mapped.xml">  
            /Person.Contact[@ContactID < 10]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="c8755-125">Der für das Zuordnungsschema (MySchema.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="c8755-125">The directory path specified for the mapping schema (MySchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="c8755-126">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c8755-126">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\sql-mapped.xml"  
    ```  
  
3.  <span data-ttu-id="c8755-127">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c8755-127">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="c8755-128">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c8755-128">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="c8755-129">Dies ist das Resultset:</span><span class="sxs-lookup"><span data-stu-id="c8755-129">This is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact ContactID="1" FirstName="Gustavo" LastName="Achong" />   
  <Person.Contact ContactID="2" FirstName="Catherine" LastName="Abel" />   
  <Person.Contact ContactID="3" FirstName="Kim" LastName="Abercrombie" />   
  <Person.Contact ContactID="4" FirstName="Humberto" LastName="Acevedo" />   
  <Person.Contact ContactID="5" FirstName="Pilar" LastName="Ackerman" />   
  <Person.Contact ContactID="6" FirstName="Frances" LastName="Adams" />   
  <Person.Contact ContactID="7" FirstName="Margaret" LastName="Smith" />   
  <Person.Contact ContactID="8" FirstName="Carla" LastName="Adams" />   
  <Person.Contact ContactID="9" FirstName="Jay" LastName="Adams" />   
</ROOT>  
```  
  
 <span data-ttu-id="c8755-130">ContactID, FirstName und LastName sind vorhanden, HomeAddress jedoch nicht, weil im Zuordnungsschema für das zugehörige `sql:mapped`-Attribut der Wert 0 (null) angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c8755-130">Note that the ContactID, FirstName, and LastName are present, but HomeAddress is not because the mapping schema specified 0 for the `sql:mapped` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8755-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8755-131">See Also</span></span>  
 [<span data-ttu-id="c8755-132">Standard Zuordnung von XSD-Elementen und-Attributen zu Tabellen und Spalten &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c8755-132">Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md)  
  
  
