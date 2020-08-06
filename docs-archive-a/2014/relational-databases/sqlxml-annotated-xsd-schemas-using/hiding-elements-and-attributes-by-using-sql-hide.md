---
title: 'Ausblenden von Elementen und Attributen mit SQL: Hide | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- hiding elements
- element mapping [SQLXML], hiding attributes and elements
- hide annotation
- sql:hide
- table/view mapping [SQLXML], hiding attributes and elements
- table mapping [SQLXML], hiding attributes and elements
- hiding attributes
- annotated XSD schemas, hiding attributes and elements
- attribute mapping [SQLXML], hiding attributes and elements
- column mapping [SQLXML]
- element hiding [SQLXML]
- XSD schemas [SQLXML], hiding attributes and elements
- attribute hiding [SQLXML]
ms.assetid: 0978301b-f068-46b6-82b9-dc555161f52e
author: rothja
ms.author: jroth
ms.openlocfilehash: 5a3beb48be1d9809b170faeafa964ba45156ac28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725350"
---
# <a name="hiding-elements-and-attributes-by-using-sqlhide"></a><span data-ttu-id="86793-102">Ausblenden von Elementen und Attributen mit sql:hide</span><span class="sxs-lookup"><span data-stu-id="86793-102">Hiding Elements and Attributes by Using sql:hide</span></span>
  <span data-ttu-id="86793-103">Wenn eine XPath-Abfrage mit einem XSD-Schema ausgeführt wird, verfügt das resultierende XML-Dokument über Elemente und Attribute, die im Schema angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="86793-103">When an XPath query is executed against an XSD schema, the resulting XML document has elements and attributes that are specified in the schema.</span></span> <span data-ttu-id="86793-104">Sie können mit der `sql:hide`-Anmerkung angeben, dass Elemente und Attribute im Schema ausgeblendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="86793-104">You can specify that some elements and attributes be hidden in the schema by using the `sql:hide` annotation.</span></span> <span data-ttu-id="86793-105">Dies ist hilfreich, wenn das Auswahlkriterium der Abfrage bestimmte Elemente oder Attribute im Schema erfordert, diese jedoch nicht im generierten XML-Dokument zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="86793-105">This is useful when the selection criteria of the query require particular elements or attributes in the schema, but you do not want them returned in the XML document that is generated.</span></span>  
  
 <span data-ttu-id="86793-106">Die `sql:hide`-Anmerkung akzeptiert einen booleschen Wert (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="86793-106">The `sql:hide` annotation takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="86793-107">Zulässig sind die Werte 0, 1, true und false.</span><span class="sxs-lookup"><span data-stu-id="86793-107">The acceptable values are 0, 1, true, and false.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="86793-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="86793-108">Examples</span></span>  
 <span data-ttu-id="86793-109">Es müssen bestimmte Anforderungen erfüllt sein, damit aus den folgenden Beispielen funktionierende Beispiele erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="86793-109">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="86793-110">Weitere Informationen finden Sie unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="86793-110">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlhide-on-an-attribute"></a><span data-ttu-id="86793-111">A.</span><span class="sxs-lookup"><span data-stu-id="86793-111">A.</span></span> <span data-ttu-id="86793-112">Angeben von sql:hide für ein Attribut</span><span class="sxs-lookup"><span data-stu-id="86793-112">Specifying sql:hide on an attribute</span></span>  
 <span data-ttu-id="86793-113">Das XSD-Schema in diesem Beispiel besteht aus einem- **\<Person.Contact>** Element mit den Attributen **ContactID**, **FirstName**und **LastName** .</span><span class="sxs-lookup"><span data-stu-id="86793-113">The XSD schema in this example consists of an **\<Person.Contact>** element with **ContactID**, **FirstName**, and **LastName** attributes.</span></span>  
  
 <span data-ttu-id="86793-114">Das **\<Person.Contact>** -Element weist einen komplexen Typ auf und wird daher der gleichnamigen Tabelle zugeordnet (Standard Zuordnung).</span><span class="sxs-lookup"><span data-stu-id="86793-114">The **\<Person.Contact>** element is of complex type and, therefore, maps to the table of the same name (default mapping).</span></span> <span data-ttu-id="86793-115">Alle Attribute des **\<Person.Contact>** -Elements sind von einem einfachen Typ und werden den Spalten mit denselben Namen in der Person. contacables in der AdventureWorks-Datenbank zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="86793-115">All the attributes of **\<Person.Contact>** element are of simple type and map to columns with the same names in the Person.Contacttable in the AdventureWorks database.</span></span> <span data-ttu-id="86793-116">Im Schema wird die-Anmerkung `sql:hide` für das **ContactID** -Attribut angegeben.</span><span class="sxs-lookup"><span data-stu-id="86793-116">In the schema, the `sql:hide` annotation is specified on the **ContactID** attribute.</span></span> <span data-ttu-id="86793-117">Wenn eine XPath-Abfrage für dieses Schema angegeben wird, wird die **ContactID** nicht im XML-Dokument zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="86793-117">When an XPath query is specified against this schema, the **ContactID** is not returned in the XML document.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID"  sql:hide="true" />   
       <xsd:attribute name="FirstName"   type="xsd:string" />   
       <xsd:attribute name="LastName"    type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="86793-118">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="86793-118">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="86793-119">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="86793-119">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="86793-120">Speichern Sie die Datei unter dem Dateinamen Hide.xml.</span><span class="sxs-lookup"><span data-stu-id="86793-120">Save the file as Hide.xml.</span></span>  
  
2.  <span data-ttu-id="86793-121">Kopieren Sie die folgende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="86793-121">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="86793-122">Speichern Sie die Datei unter dem Namen HideT.xml in dem Verzeichnis, in dem Sie zuvor Hide.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="86793-122">Save the file as HideT.xml in the same directory where you saved Hide.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="Hide.xml">  
            /Person.Contact[@ContactID="1"]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="86793-123">Der für das Zuordnungschema (Hide.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="86793-123">The directory path specified for the mapping schema (Hide.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="86793-124">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="86793-124">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\Hide.xml"  
    ```  
  
3.  <span data-ttu-id="86793-125">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="86793-125">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="86793-126">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="86793-126">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="86793-127">Im Folgenden wird das Resultset aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="86793-127">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <Person.Contact FirstName="Gustavo" LastName="Achong" />   
</ROOT>  
```  
  
 <span data-ttu-id="86793-128">Wenn `sql:hide` für ein Element angegeben wird, werden das betreffende Element und dessen Attribute oder untergeordneten Elemente nicht im generierten XML-Dokument ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="86793-128">When `sql:hide` is specified on an element, the element and its attributes or child elements do not appear in the XML document that is generated.</span></span> <span data-ttu-id="86793-129">Im folgenden finden Sie ein weiteres XSD-Schema, in dem `sql:hide` für das-Element angegeben wird **\<OD>** :</span><span class="sxs-lookup"><span data-stu-id="86793-129">Here is another XSD schema in which `sql:hide` is specified on the **\<OD>** element:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:annotation>  
    <xsd:documentation>  
      Sales.Customer-Sales.SalesOrderHeader-Sales.SalesOrderDetail Schema  
      Copyright 2004 Microsoft. All rights reserved.  
    </xsd:documentation>  
    <xsd:appinfo>  
      <sql:relationship name="CustomerOrder"  
         parent="Sales.Customer"  
                  parent-key="CustomerID"  
                  child-key="CustomerID"  
                  child="Sales.SalesOrderHeader" />  
       <sql:relationship name="OrderOrderDetails"  
                  parent="Sales.SalesOrderHeader"  
                  parent-key="SalesOrderID"  
                  child-key="SalesOrderID"  
                  child="Sales.SalesOrderDetail"/>  
    </xsd:appinfo>  
  </xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Sales.Customer">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"   
                     maxOccurs="unbounded"   
                     sql:relationship="CustomerOrder">  
          <xsd:complexType>  
            <xsd:sequence>  
               <xsd:element name="OD" sql:relation="Sales.SalesOrderDetail"                                       maxOccurs="unbounded"                                       sql:relationship="OrderOrderDetails"                                       sql:hide="1">  
                  <xsd:complexType>  
                    <xsd:attribute name="SalesOrderID" type="xsd:string"/>  
                    <xsd:attribute name="ProductID" type="xsd:string"/>  
                  </xsd:complexType>  
               </xsd:element>  
            </xsd:sequence>  
          <xsd:attribute name="CustomerID" type="xsd:string"/>  
          <xsd:attribute name="OID" sql:field="SalesOrderID"   
                                    type="xsd:string"/>  
          <xsd:attribute name="OrderDate" type="xsd:date"/>   
        </xsd:complexType>  
      </xsd:element>  
    </xsd:sequence>  
    <xsd:attribute name="CID" sql:field="CustomerID"   
                                type="xsd:string"/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="86793-130">Wenn eine XPath-Abfrage (z. b. `/Customers[@CID="1"]` ) für dieses Schema angegeben wird, schließt das generierte XML-Dokument das **\<OD>** -Element und seine untergeordneten Elemente nicht ein, wie in diesem partiellen Ergebnis gezeigt:</span><span class="sxs-lookup"><span data-stu-id="86793-130">When an XPath query (for example `/Customers[@CID="1"]`) is specified against this schema, the XML document that is generated does not include the **\<OD>** element and its children, as shown in this partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customers CID="1">  
    <Order CustomerID="1" OID="43860" OrderDate="2001-08-01" />   
    <Order CustomerID="1" OID="44501" OrderDate="2001-11-01" />   
    <Order CustomerID="1" OID="45283" OrderDate="2002-02-01" />   
    <Order CustomerID="1" OID="46042" OrderDate="2002-05-01" />   
  </Customers>  
</ROOT>  
```  
  
  
