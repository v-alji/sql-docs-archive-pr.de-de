---
title: 'Identifizieren von Schlüssel Spalten mithilfe von SQL: key-fields (SQLXML 4,0) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- nesting XML results
- proper nesting in results [SQLXML]
- sql:key-fields
- XSD schemas [SQLXML], key columns
- identifying key columns [SQLXML]
- annotated XSD schemas, key columns
- key columns [SQLXML]
- relationships [SQLXML], key columns
- hierarchical relationships [SQLXML]
- key-fields annotation
ms.assetid: 1a5ad868-8602-45c4-913d-6fbb837eebb0
author: rothja
ms.author: jroth
ms.openlocfilehash: 0ab12b34874a54bad2e08a96d08ebd0cc994f946
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725345"
---
# <a name="identifying-key-columns-using-sqlkey-fields-sqlxml-40"></a><span data-ttu-id="761ea-102">Identifizieren von Schlüsselspalten mithilfe von sql:key-Feldern (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="761ea-102">Identifying Key Columns Using sql:key-fields (SQLXML 4.0)</span></span>
  <span data-ttu-id="761ea-103">Wenn eine XPath-Abfrage für ein XSD-Schema angegeben wird, sind in den meisten Fällen wichtige Informationen erforderlich, um eine ordnungsgemäße Schachtelung im Ergebnis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="761ea-103">When an XPath query is specified against an XSD schema, key information is required in most cases to obtain proper nesting in the result.</span></span> <span data-ttu-id="761ea-104">Durch die Angabe der `sql:key-fields`-Anmerkung lässt sich sicherstellen, dass die entsprechende Hierarchie generiert wird.</span><span class="sxs-lookup"><span data-stu-id="761ea-104">Specifying the `sql:key-fields` annotation is a way of ensuring that the appropriate hierarchy is generated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="761ea-105">Um die richtige Schachtelung sicherzustellen, wird empfohlen, `sql:key-fields` für diejenigen Elemente anzugeben, die Tabellen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="761ea-105">To ensure proper nesting, it is recommended that you specify `sql:key-fields` for elements that map to tables.</span></span> <span data-ttu-id="761ea-106">Das erzeugte XML wird durch die Anordnung des zugrunde liegenden Resultsets beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="761ea-106">The XML produced is sensitive to the ordering of the underlying result set.</span></span> <span data-ttu-id="761ea-107">Wenn `sql:key-fields` nicht angegeben wird, hat das generierte XML unter Umständen nicht das richtige Format.</span><span class="sxs-lookup"><span data-stu-id="761ea-107">If `sql:key-fields` is not specified, the XML generated might not be formed properly.</span></span>  
  
 <span data-ttu-id="761ea-108">Der Wert von `sql:key-fields` identifiziert die Spalte(n), welche die Zeilen in der Beziehung eindeutig identifiziert bzw. identifizieren.</span><span class="sxs-lookup"><span data-stu-id="761ea-108">The value of `sql:key-fields` identifies the column(s) that uniquely identify the rows in the relation.</span></span> <span data-ttu-id="761ea-109">Wenn mehrere Spalten zur eindeutigen Identifizierung einer Zeile erforderlich sind, werden die Spaltenwerte jeweils durch ein Leerzeichen voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="761ea-109">If more than one column is required to uniquely identify a row, the column values are delimited by spaces.</span></span>  
  
 <span data-ttu-id="761ea-110">Sie müssen die-Anmerkung verwenden `sql:key-fields` , wenn ein-Element ein-Element enthält **\<sql:relationship>** , das zwischen dem-Element und einem untergeordneten-Element definiert ist, aber nicht den Primärschlüssel der im übergeordneten Element angegebenen Tabelle bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="761ea-110">You must use the `sql:key-fields` annotation when an element contains a **\<sql:relationship>** that is defined between the element and a child element but does not provide the primary key of the table that is specified in the parent element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="761ea-111">Beispiele</span><span class="sxs-lookup"><span data-stu-id="761ea-111">Examples</span></span>  
 <span data-ttu-id="761ea-112">Es müssen bestimmte Anforderungen erfüllt sein, damit aus den folgenden Beispielen funktionierende Beispiele erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="761ea-112">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="761ea-113">Weitere Informationen finden Sie unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="761ea-113">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-producing-the-appropriate-nesting-when-sqlrelationship-does-not-provide-sufficient-information"></a><span data-ttu-id="761ea-114">A.</span><span class="sxs-lookup"><span data-stu-id="761ea-114">A.</span></span> <span data-ttu-id="761ea-115">Erzeugen der passenden Schachtelung, wenn \<sql:relationship> keine ausreichenden Informationen bereitstellt</span><span class="sxs-lookup"><span data-stu-id="761ea-115">Producing the appropriate nesting when \<sql:relationship> does not provide sufficient information</span></span>  
 <span data-ttu-id="761ea-116">Dieses Beispiel zeigt, wo `sql:key-fields` angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="761ea-116">This example shows where `sql:key-fields` must be specified.</span></span>  
  
 <span data-ttu-id="761ea-117">Betrachten Sie folgendes Schema.</span><span class="sxs-lookup"><span data-stu-id="761ea-117">Consider the following schema.</span></span> <span data-ttu-id="761ea-118">Das Schema gibt eine Hierarchie zwischen dem **\<Order>** -Element und dem- **\<Customer>** Element an, in dem das- **\<Order>** Element das übergeordnete Element ist **\<Customer>**</span><span class="sxs-lookup"><span data-stu-id="761ea-118">The schema specifies a hierarchy between the **\<Order>** and **\<Customer>** elements in which the **\<Order>** element is the parent and the **\<Customer>** element is a child.</span></span>  
  
 <span data-ttu-id="761ea-119">Das **\<sql:relationship>** -Tag wird verwendet, um die Beziehung zwischen übergeordneten und untergeordneten Elementen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="761ea-119">The **\<sql:relationship>** tag is used to specify the parent-child relationship.</span></span> <span data-ttu-id="761ea-120">In diesem Tag wird CustomerID als übergeordneter Schlüssel identifiziert, der auf die untergeordnete CustomerID-Schlüsselspalte in der Sales.Customer-Tabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="761ea-120">It identifies CustomerID in the Sales.SalesOrderHeader table as the parent key that refers to the CustomerID child key in the Sales.Customer table.</span></span> <span data-ttu-id="761ea-121">Die in bereitgestellten Informationen **\<sql:relationship>** reichen nicht aus, um Zeilen in der übergeordneten Tabelle (Sales. SalesOrderHeader) eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="761ea-121">The information provided in **\<sql:relationship>** is not sufficient to uniquely identify rows in the parent table (Sales.SalesOrderHeader).</span></span> <span data-ttu-id="761ea-122">Ohne die `sql:key-fields`-Anmerkung wird daher eine ungenaue Hierarchie generiert.</span><span class="sxs-lookup"><span data-stu-id="761ea-122">Therefore, without the `sql:key-fields` annotation, the hierarchy that is generated is inaccurate.</span></span>  
  
 <span data-ttu-id="761ea-123">Bei Angabe `sql:key-fields` von für **\<Order>** identifiziert die Anmerkung die Zeilen in der übergeordneten Tabelle (Sales. SalesOrderHeader-Tabelle) eindeutig, und die untergeordneten Elemente werden unter dem übergeordneten Element angezeigt.</span><span class="sxs-lookup"><span data-stu-id="761ea-123">With `sql:key-fields` specified on **\<Order>**, the annotation uniquely identifies the rows in the parent (Sales.SalesOrderHeader table), and its child elements appear below its parent.</span></span>  
  
 <span data-ttu-id="761ea-124">Das ist das Schema:</span><span class="sxs-lookup"><span data-stu-id="761ea-124">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrdCust"  
        parent="Sales.SalesOrderHeader"  
        parent-key="CustomerID"  
        child="Sales.Customer"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"   
               sql:key-fields="SalesOrderID">  
   <xsd:complexType>  
     <xsd:sequence>  
     <xsd:element name="Customer" sql:relation="Sales.Customer"   
                       sql:relationship="OrdCust"  >  
       <xsd:complexType>  
         <xsd:attribute name="CustID" sql:field="CustomerID" />  
         <xsd:attribute name="SoldBy" sql:field="SalesPersonID" />  
       </xsd:complexType>  
     </xsd:element>  
     </xsd:sequence>  
     <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
     <xsd:attribute name= "CustomerID" type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="761ea-125">So erstellen Sie ein funktionstüchtiges Beispiel für dieses Schema</span><span class="sxs-lookup"><span data-stu-id="761ea-125">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="761ea-126">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="761ea-126">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="761ea-127">Speichern Sie die Datei unter dem Dateinamen KeyFields1.xml.</span><span class="sxs-lookup"><span data-stu-id="761ea-127">Save the file as KeyFields1.xml.</span></span>  
  
2.  <span data-ttu-id="761ea-128">Kopieren Sie die folgende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="761ea-128">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="761ea-129">Speichern Sie die Datei unter dem Namen KeyFields1T.xml im gleichen Verzeichnis, in dem Sie KeyFields1.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="761ea-129">Save the file as KeyFields1T.xml in the same directory where you saved KeyFields1.xml.</span></span> <span data-ttu-id="761ea-130">Die XPath-Abfrage in der Vorlage gibt alle-Elemente zurück, deren **\<Order>** CustomerID-Wert kleiner als 3 ist.</span><span class="sxs-lookup"><span data-stu-id="761ea-130">The XPath query in the template returns all the **\<Order>** elements with a CustomerID of less than 3.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="KeyFields1.xml">  
            /Order[@CustomerID < 3]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="761ea-131">Der für das Zuordnungsschema (KeyFields1.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="761ea-131">The directory path specified for the mapping schema (KeyFields1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="761ea-132">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="761ea-132">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\KeyFields1.xml"  
    ```  
  
3.  <span data-ttu-id="761ea-133">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="761ea-133">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="761ea-134">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="761ea-134">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="761ea-135">Im Folgenden wird ein Teil des Resultsets aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="761ea-135">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
    <Order SalesOrderID="43860" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    <Order SalesOrderID="44501" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    <Order SalesOrderID="45283" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    .....  
</ROOT>  
```  
  
### <a name="b-specifying-sqlkey-fields-to-produce-proper-nesting-in-the-result"></a><span data-ttu-id="761ea-136">B.</span><span class="sxs-lookup"><span data-stu-id="761ea-136">B.</span></span> <span data-ttu-id="761ea-137">Angeben der sql:key-Felder, um die richtige Schachtelung im Ergebnis zu erzeugen</span><span class="sxs-lookup"><span data-stu-id="761ea-137">Specifying sql:key-fields to produce proper nesting in the result</span></span>  
 <span data-ttu-id="761ea-138">Im folgenden Schema gibt es keine Hierarchie, die mit angegeben wird **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="761ea-138">In the following schema, there is no hierarchy specified using **\<sql:relationship>**.</span></span> <span data-ttu-id="761ea-139">Das Schema erfordert trotzdem die Angabe der `sql:key-fields`-Anmerkung, um Mitarbeiter in der HumanResources.Employee-Tabelle eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="761ea-139">The schema still requires specifying the `sql:key-fields` annotation to uniquely identify employees in the HumanResources.Employee table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="HumanResources.Employee" sql:key-fields="EmployeeID" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Title">  
          <xsd:complexType>  
            <xsd:simpleContent>  
              <xsd:extension base="xsd:string">  
                 <xsd:attribute name="EmployeeID" type="xsd:integer" />  
              </xsd:extension>  
            </xsd:simpleContent>  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
   </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="761ea-140">So erstellen Sie ein funktionstüchtiges Beispiel für dieses Schema</span><span class="sxs-lookup"><span data-stu-id="761ea-140">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="761ea-141">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="761ea-141">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="761ea-142">Speichern Sie die Datei unter dem Dateinamen KeyFields2.xml.</span><span class="sxs-lookup"><span data-stu-id="761ea-142">Save the file as KeyFields2.xml.</span></span>  
  
2.  <span data-ttu-id="761ea-143">Kopieren Sie die folgende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="761ea-143">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="761ea-144">Speichern Sie die Datei unter dem Namen KeyFields2T.xml im gleichen Verzeichnis, in dem Sie KeyFields2.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="761ea-144">Save the file as KeyFields2T.xml in the same directory where you saved KeyFields2.xml.</span></span> <span data-ttu-id="761ea-145">Die XPath-Abfrage in der Vorlage gibt alle **\<HumanResources.Employee>** Elemente zurück:</span><span class="sxs-lookup"><span data-stu-id="761ea-145">The XPath query in the template returns all the **\<HumanResources.Employee>** elements:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="KeyFields2.xml">  
        /HumanResources.Employee  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="761ea-146">Der für das Zuordnungsschema (KeyFields2.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="761ea-146">The directory path specified for the mapping schema (KeyFields2.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="761ea-147">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="761ea-147">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\KeyFields2.xml"  
    ```  
  
3.  <span data-ttu-id="761ea-148">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="761ea-148">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="761ea-149">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="761ea-149">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="761ea-150">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="761ea-150">This is the result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <HumanResources.Employee>  
    <Title EmployeeID="1">Production Technician - WC60</Title>   
  </HumanResources.Employee>  
  <HumanResources.Employee>  
    <Title EmployeeID="2">Marketing Assistant</Title>   
  </HumanResources.Employee>  
  <HumanResources.Employee>  
    <Title EmployeeID="3">Engineering Manager</Title>   
  </HumanResources.Employee>  
  ...  
</ROOT>  
```  
  
  
