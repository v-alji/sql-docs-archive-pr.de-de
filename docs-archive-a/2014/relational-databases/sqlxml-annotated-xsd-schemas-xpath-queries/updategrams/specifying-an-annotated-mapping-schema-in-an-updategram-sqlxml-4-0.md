---
title: Angeben eines Mapping-Schemas mit Anmerkungen in einem Update Gram (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, updategrams
- data types [SQLXML], mapping schema in updategrams
- updategrams [SQLXML], annotated mapping schemas
- annotated XDR schemas, updategrams
- inverse attribute
- parent-child relationships [SQLXML]
- mapping-schema attribute
- mapping schema [SQLXML], updategrams
- sql:inverse
ms.assetid: 2e266ed9-4cfb-434a-af55-d0839f64bb9a
author: rothja
ms.author: jroth
ms.openlocfilehash: a181b3081b51cca160709703364c248e495e0214
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619738"
---
# <a name="specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-40"></a><span data-ttu-id="f3fa8-102">Angeben eines Zuordnungsschemas mit Anmerkungen in einem Updategram (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="f3fa8-102">Specifying an Annotated Mapping Schema in an Updategram (SQLXML 4.0)</span></span>
  <span data-ttu-id="f3fa8-103">In diesem Thema wird erläutert, wie das in einem Updategram angegebene Zuordnungsschema (XSD oder XDR) zur Verarbeitung von Updates verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-103">This topic explains how the mapping schema (XSD or XDR) that is specified in an updategram is used to process the updates.</span></span> <span data-ttu-id="f3fa8-104">In einem Update Gram können Sie den Namen eines Zuordnungsschemas bereitstellen, das bei der Zuordnung der Elemente und Attribute im Update Gram zu Tabellen und Spalten in verwendet werden soll [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f3fa8-104">In an updategram, you can provide the name of an annotated mapping schema to use in mapping the elements and attributes in the updategram to tables and columns in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f3fa8-105">Wenn in einem Updategram ein Zuordnungsschema angegeben ist, müssen die im Updategram festgelegten Element- und Attributnamen den Elementen und Attributen im Zuordnungsschema zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-105">When a mapping schema is specified in an updategram, the element and attribute names that are specified in the updategram must map to the elements and attributes in the mapping schema.</span></span>  
  
 <span data-ttu-id="f3fa8-106">Um ein Zuordnungsschema anzugeben, verwenden Sie das- `mapping-schema` Attribut des- **\<sync>** Elements.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-106">To specify a mapping schema, you use the `mapping-schema` attribute of the **\<sync>** element.</span></span> <span data-ttu-id="f3fa8-107">Die folgenden Beispiele zeigen zwei Updategrams: ein Updategram, das ein einfaches Zuordnungsschema verwendet, und ein Updategram, das ein komplexeres Schema verwendet.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-107">The following examples show two updategrams: one that uses a simple mapping schema, and one that uses a more complex schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3fa8-108">Diese Dokumentation setzt voraus, dass Sie mit Vorlagen und der Unterstützung von Zuordnungsschemas in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-108">This documentation assumes that you are familiar with templates and mapping schema support in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f3fa8-109">Weitere Informationen finden Sie unter [Einführung in XSD-Schemas mit Anmerkungen &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="f3fa8-109">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="f3fa8-110">Informationen zu Legacy Anwendungen, die XDR verwenden, finden Sie unter mit Anmerkungen versehene [XDR-Schemas &#40;in SQLXML 4,0&#41;veraltet ](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="f3fa8-110">For legacy applications that use XDR, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="dealing-with-data-types"></a><span data-ttu-id="f3fa8-111">Umgehen mit Datentypen</span><span class="sxs-lookup"><span data-stu-id="f3fa8-111">Dealing with Data Types</span></span>  
 <span data-ttu-id="f3fa8-112">Wenn das Schema den `image` -, `binary` -oder `varbinary` [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datentyp (mithilfe von `sql:datatype` ) angibt und keinen XML-Datentyp angibt, geht das Update Gram davon aus, dass der XML-Datentyp ist `binary base 64` .</span><span class="sxs-lookup"><span data-stu-id="f3fa8-112">If the schema specifies the `image`, `binary`, or `varbinary`[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type (by using `sql:datatype`) and does not specify an XML data type, the updategram assumes that the XML data type is `binary base 64`.</span></span> <span data-ttu-id="f3fa8-113">Wenn Ihre Daten vom Typ `bin.base` sind, müssen Sie den Typ (`dt:type=bin.base` oder `type="xsd:hexBinary"`) explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-113">If your data is `bin.base` type, you must explicitly specify the type (`dt:type=bin.base` or `type="xsd:hexBinary"`).</span></span>  
  
 <span data-ttu-id="f3fa8-114">Wenn das Schema den `dateTime`-Datentyp, den `date`-Datentyp oder den `time`-XSD-Datentyp angibt, müssen Sie auch den entsprechenden [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Datentyp mit `sql:datatype="dateTime"` festlegen.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-114">If the schema specifies the `dateTime`, `date`, or `time` XSD data type, you must also specify the corresponding [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type by using `sql:datatype="dateTime"`.</span></span>  
  
 <span data-ttu-id="f3fa8-115">Beim Verarbeiten von Parametern des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `money` Typs müssen Sie explizit `sql:datatype="money"` auf dem entsprechenden Knoten im Zuordnungsschema angeben.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-115">When handling parameters of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `money` type, you must explicitly specify `sql:datatype="money"` on the appropriate node in the mapping schema.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f3fa8-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f3fa8-116">Examples</span></span>  
 <span data-ttu-id="f3fa8-117">Wenn Sie in den folgenden Beispielen funktionierende Beispiele erstellen möchten, müssen Sie die unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../../sqlxml/requirements-for-running-sqlxml-examples.md)angegebenen Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-117">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-creating-an-updategram-with-a-simple-mapping-schema"></a><span data-ttu-id="f3fa8-118">A.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-118">A.</span></span> <span data-ttu-id="f3fa8-119">Erstellen eines Updategrams mit einem einfachen Zuordnungsschema</span><span class="sxs-lookup"><span data-stu-id="f3fa8-119">Creating an updategram with a simple mapping schema</span></span>  
 <span data-ttu-id="f3fa8-120">Das folgende XSD-Schema (SampleSchema.xml) ist ein Zuordnungs Schema, das das- **\<Customer>** Element der Sales. Customer-Tabelle zuordnet:</span><span class="sxs-lookup"><span data-stu-id="f3fa8-120">The following XSD schema (SampleSchema.xml) is a mapping schema that maps the **\<Customer>** element to the Sales.Customer table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
        <xsd:attribute name="CustID"    
                       sql:field="CustomerID"   
                       type="xsd:string" />  
        <xsd:attribute name="RegionID"    
                       sql:field="TerritoryID"    
                       type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="f3fa8-121">Das folgende Updategram fügt einen Datensatz in die Sales.Customer-Tabelle ein und ordnet diese Daten anhand des vorherigen Zuordnungsschemas der Tabelle ordnungsgemäß zu.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-121">The following updategram inserts a record into the Sales.Customer table and relies on the previous mapping schema to properly map this data to the table.</span></span> <span data-ttu-id="f3fa8-122">Beachten Sie, dass für das Update Gram derselbe Elementname verwendet wird, der **\<Customer>** im Schema definiert ist.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-122">Notice that the updategram uses the same element name, **\<Customer>**, as defined in the schema.</span></span> <span data-ttu-id="f3fa8-123">Dies ist obligatorisch, da das Updategram ein bestimmtes Schema angibt.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-123">This is mandatory because the updategram specifies a particular schema.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="f3fa8-124">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="f3fa8-124">To test the updategram</span></span>  
  
1.  <span data-ttu-id="f3fa8-125">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-125">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="f3fa8-126">Speichern Sie die Datei unter dem Dateinamen SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-126">Save the file as SampleUpdateSchema.xml.</span></span>  
  
2.  <span data-ttu-id="f3fa8-127">Kopieren Sie die unten stehende Updategramvorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-127">Copy the updategram template below and paste it into a text file.</span></span> <span data-ttu-id="f3fa8-128">Speichern Sie die Datei unter dem Namen SampleUpdategram.xml im gleichen Verzeichnis, in dem Sie SampleUpdateSchema.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-128">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleUpdateSchema.xml">  
        <updg:before>  
          <Customer CustID="1" RegionID="1"  />  
        </updg:before>  
        <updg:after>  
          <Customer CustID="1" RegionID="2" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="f3fa8-129">Der für das Zuordnungschema (SampleUpdateSchema.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-129">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="f3fa8-130">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f3fa8-130">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
3.  <span data-ttu-id="f3fa8-131">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-131">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="f3fa8-132">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="f3fa8-132">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="f3fa8-133">Dies ist das entsprechende XDR-Schema:</span><span class="sxs-lookup"><span data-stu-id="f3fa8-133">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
   <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
         xmlns:dt="urn:schemas-microsoft-com:datatypes"   
         xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
     <ElementType name="Customer" sql:relation="Sales.Customer" >  
       <AttributeType name="CustID" />  
       <AttributeType name="RegionID" />  
  
       <attribute type="CustID" sql:field="CustomerID" />  
       <attribute type="RegionID" sql:field="TerritoryID" />  
     </ElementType>  
   </Schema>   
```  
  
### <a name="b-inserting-a-record-by-using-the-parent-child-relationship-specified-in-the-mapping-schema"></a><span data-ttu-id="f3fa8-134">B.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-134">B.</span></span> <span data-ttu-id="f3fa8-135">Einfügen eines Datensatzes durch Verwenden der im Zuordnungsschema angegebenen Über-/Unterordnungsbeziehung</span><span class="sxs-lookup"><span data-stu-id="f3fa8-135">Inserting a record by using the parent-child relationship specified in the mapping schema</span></span>  
 <span data-ttu-id="f3fa8-136">Schemaelemente können in Beziehung gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-136">Schema elements can be related.</span></span> <span data-ttu-id="f3fa8-137">Das **\<sql:relationship>** -Element gibt die über-/Unterordnungsbeziehung zwischen den Schema Elementen an.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-137">The **\<sql:relationship>** element specifies the parent-child relationship between the schema elements.</span></span> <span data-ttu-id="f3fa8-138">Mit diesen Informationen werden die entsprechenden Tabellen aktualisiert, die Primärschlüssel-Fremdschlüssel-Beziehungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-138">This information is used to update corresponding tables that have primary-key/foreign-key relationship.</span></span>  
  
 <span data-ttu-id="f3fa8-139">Das folgende Mapping-Schema (SampleSchema.xml) besteht aus zwei Elementen **\<Order>** **\<OD>** : und:</span><span class="sxs-lookup"><span data-stu-id="f3fa8-139">The following mapping schema (SampleSchema.xml) consists of two elements, **\<Order>** and **\<OD>**:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="OD"   
                     sql:relation="Sales.SalesOrderDetail"  
                     sql:relationship="OrderOD" >  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID"   type="xsd:integer" />  
              <xsd:attribute name="ProductID" type="xsd:integer" />  
             <xsd:attribute name="UnitPrice"  type="xsd:decimal" />  
             <xsd:attribute name="OrderQty"   type="xsd:integer" />  
             <xsd:attribute name="UnitPriceDiscount"   type="xsd:decimal" />  
  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
        <xsd:attribute name="SalesOrderID"  type="xsd:integer" />  
        <xsd:attribute name="OrderDate"  type="xsd:date" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="f3fa8-140">Das folgende Update Gram verwendet dieses XSD-Schema, um einen neuen Bestell Detaildaten Satz (ein- **\<OD>** Element im- **\<after>** Block) für die Bestellung 43860 hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-140">The following updategram uses this XSD schema to add a new order detail record (an **\<OD>** element in the **\<after>** block) for order 43860.</span></span> <span data-ttu-id="f3fa8-141">Das `mapping-schema`-Attribut dient zur Angabe des Zuordnungsschemas im Updategram.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-141">The `mapping-schema` attribute is used to specify the mapping schema in the updategram.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="SampleUpdateSchema.xml" >  
    <updg:before>  
       <Order SalesOrderID="43860" />  
    </updg:before>  
    <updg:after>  
      <Order SalesOrderID="43860" >  
           <OD ProductID="753" UnitPrice="$10.00"  
               Quantity="5" Discount="0.0" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="f3fa8-142">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="f3fa8-142">To test the updategram</span></span>  
  
1.  <span data-ttu-id="f3fa8-143">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-143">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="f3fa8-144">Speichern Sie die Datei unter dem Dateinamen SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-144">Save the file as SampleUpdateSchema.xml.</span></span>  
  
2.  <span data-ttu-id="f3fa8-145">Kopieren Sie die oben stehende Updategramvorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-145">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="f3fa8-146">Speichern Sie die Datei unter dem Namen SampleUpdategram.xml im gleichen Verzeichnis, in dem Sie SampleUpdateSchema.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-146">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
     <span data-ttu-id="f3fa8-147">Der für das Zuordnungschema (SampleUpdateSchema.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-147">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="f3fa8-148">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f3fa8-148">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
3.  <span data-ttu-id="f3fa8-149">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-149">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="f3fa8-150">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="f3fa8-150">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="f3fa8-151">Dies ist das entsprechende XDR-Schema:</span><span class="sxs-lookup"><span data-stu-id="f3fa8-151">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  
<ElementType name="OD" sql:relation="Sales.SalesOrderDetail" >  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="ProductID" />  
    <AttributeType name="UnitPrice"  dt:type="fixed.14.4" />  
    <AttributeType name="OrderQty" />  
    <AttributeType name="UnitPriceDiscount" />  
  
    <attribute type="SalesOrderID" />  
    <attribute type="ProductID" />  
    <attribute type="UnitPrice" />  
    <attribute type="OrderQty" />  
    <attribute type="UnitPriceDiscount" />  
</ElementType>  
  
<ElementType name="Order" sql:relation="Sales.SalesOrderHeader" >  
    <AttributeType name="CustomerID" />  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="OrderDate" />  
  
    <attribute type="CustomerID" />  
    <attribute type="SalesOrderID" />  
    <attribute type="OrderDate" />  
    <element type="OD" >  
             <sql:relationship   
                   key-relation="Sales.SalesOrderHeader"  
                   key="SalesOrderID"  
                   foreign-key="SalesOrderID"  
                   foreign-relation="Sales.SalesOrderDetail" />  
    </element>  
</ElementType>  
</Schema>  
```  
  
### <a name="c-inserting-a-record-by-using-the-parent-child-relationship-and-inverse-annotation-specified-in-the-xsd-schema"></a><span data-ttu-id="f3fa8-152">C.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-152">C.</span></span> <span data-ttu-id="f3fa8-153">Einfügen eines Datensatzes durch Verwenden der im XSD-Schema angegebenen Über-/Unterordnungsbeziehung und der inverse-Anmerkung</span><span class="sxs-lookup"><span data-stu-id="f3fa8-153">Inserting a record by using the parent-child relationship and inverse annotation specified in the XSD schema</span></span>  
 <span data-ttu-id="f3fa8-154">Dieses Beispiel veranschaulicht, wie die Updategramlogik die im XSD-Schema angegebene Über-/Unterordnungsbeziehung zur Verarbeitung von Updates verwendet und wie die `inverse`-Anmerkung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-154">This example illustrates how the updategram logic uses the parent-child relationship specified in the XSD to process updates, and how the `inverse` annotation is used.</span></span> <span data-ttu-id="f3fa8-155">Weitere Informationen zur-Anmerkung `inverse` finden Sie unter [angeben des SQL: inverse-Attributs für SQL: Relationship &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="f3fa8-155">For more information about the `inverse` annotation, see [Specifying the sql:inverse Attribute on sql:relationship &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="f3fa8-156">In diesem Beispiel wird davon ausgegangen, dass sich die folgenden Tabellen in der **tempdb** -Datenbank befinden:</span><span class="sxs-lookup"><span data-stu-id="f3fa8-156">This example assumes that the following tables are in the **tempdb** database:</span></span>  
  
-   <span data-ttu-id="f3fa8-157">`Cust (CustomerID, CompanyName)`, wobei `CustomerID` der Primärschlüssel ist</span><span class="sxs-lookup"><span data-stu-id="f3fa8-157">`Cust (CustomerID, CompanyName)`, where `CustomerID` is the primary key</span></span>  
  
-   <span data-ttu-id="f3fa8-158">`Ord (OrderID, CustomerID)`, wobei `CustomerID` ein Fremdschlüssel ist, der auf den `CustomerID` Primärschlüssel in der `Cust`-Tabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-158">`Ord (OrderID, CustomerID)`, where `CustomerID` is a foreign key that refers to the `CustomerID` primary key in the `Cust` table.</span></span>  
  
 <span data-ttu-id="f3fa8-159">Das Updategram verwendet das folgende XSD-Schema, um Datensätze in die Cust und Ord-Tabellen einzufügen:</span><span class="sxs-lookup"><span data-stu-id="f3fa8-159">The updategram uses the following XSD schema to insert records into the Cust and Ord tables :</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
       <sql:relationship name="OrdCust" inverse="true"  
                  parent="Ord"  
                  parent-key="CustomerID"  
                  child-key="CustomerID"  
                  child="Cust"/>  
  </xsd:appinfo>  
</xsd:annotation>  
  
<xsd:element name="Order" sql:relation="Ord">  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element ref="Customer" sql:relationship="OrdCust"/>  
    </xsd:sequence>  
    <xsd:attribute name="OrderID"   type="xsd:int"/>  
    <xsd:attribute name="CustomerID" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:element>  
  
<xsd:element name="Customer" sql:relation="Cust">  
  <xsd:complexType>  
     <xsd:attribute name="CustomerID"  type="xsd:string"/>  
    <xsd:attribute name="CompanyName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:element>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="f3fa8-160">Das XSD-Schema in diesem Beispiel verfügt über die **\<Customer>** **\<Order>** Elemente und und gibt eine über-/Unterordnungsbeziehung zwischen den beiden Elementen an.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-160">The XSD schema in this example has **\<Customer>** and **\<Order>** elements, and it specifies a parent-child relationship between the two elements.</span></span> <span data-ttu-id="f3fa8-161">Sie identifiziert **\<Order>** als übergeordnetes Element und **\<Customer>** als untergeordnetes Element.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-161">It identifies **\<Order>** as the parent element and **\<Customer>** as the child element.</span></span>  
  
 <span data-ttu-id="f3fa8-162">Die Verarbeitungslogik des Updategrams bestimmt mit den Informationen über die Über-/Unterordnungsbeziehung die Reihenfolge, in der die Datensätze in die Tabellen eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-162">The updategram processing logic uses the information about the parent-child relationship to determine the order in which records are inserted into tables.</span></span> <span data-ttu-id="f3fa8-163">In diesem Beispiel versucht die Update Gram Logik zuerst, einen Datensatz in die Ord-Tabelle einzufügen (da **\<Order>** das übergeordnete Element ist), und versucht dann, einen Datensatz in die Cust-Tabelle einzufügen (da **\<Customer>** das untergeordnete Element ist).</span><span class="sxs-lookup"><span data-stu-id="f3fa8-163">In this example, the updategram logic first attempts to insert a record into the Ord table (because **\<Order>** is the parent) and then attempts to insert a record into the Cust table (because **\<Customer>** is the child).</span></span> <span data-ttu-id="f3fa8-164">Aufgrund der Primärschlüssel-Fremdschlüssel-Informationen, die im Datenbanktabellenschema enthalten sind, verursacht dieser Einfügevorgang jedoch eine Fremdschlüsselverletzung in der Datenbank und der Vorgang schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-164">However, because of the primary key/foreign key information that is contained in the database table schema, this insert operation causes a foreign key violation in the database and the insert fails.</span></span>  
  
 <span data-ttu-id="f3fa8-165">Um die Update Gram Logik anzuweisen, die über-/Unterordnungsbeziehung während des Aktualisierungs Vorgangs umzukehren, wird die-Anmerkung `inverse` für das- **\<relationship>** Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-165">To instruct the updategram logic to reverse the parent-child relationship during the update operation, the `inverse` annotation is specified on the **\<relationship>** element.</span></span> <span data-ttu-id="f3fa8-166">Als Folge werden die Datensätze zuerst in die Cust-Tabelle und anschließend in die Ord-Tabelle eingefügt, und der Vorgang wird erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-166">As a result, records are added first in the Cust table and then in the Ord table, and the operation succeeds.</span></span>  
  
 <span data-ttu-id="f3fa8-167">Das folgende Updategram fügt mit dem angegebenen XSD-Schema einen Auftrag (OrderID=2) in die Ord-Tabelle ein und einen Kunden (CustomerID='AAAAA') in die Cust-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-167">The following updategram inserts an order (OrderID=2) in the Ord table and a customer (CustomerID='AAAAA') in the Cust table by using the specified XSD schema:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="SampleUpdateSchema.xml" >  
    <updg:before/>  
    <updg:after>  
      <Order OrderID="2" CustomerID="AAAAA" >  
        <Customer CustomerID="AAAAA" CompanyName="AAAAA Company" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="f3fa8-168">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="f3fa8-168">To test the updategram</span></span>  
  
1.  <span data-ttu-id="f3fa8-169">Erstellen Sie diese Tabellen in der **tempdb** -Datenbank:</span><span class="sxs-lookup"><span data-stu-id="f3fa8-169">Create these tables in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Cust(CustomerID varchar(5) primary key,   
                      CompanyName varchar(20))  
    GO  
    CREATE TABLE Ord (OrderID int primary key,   
                      CustomerID varchar(5) references Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="f3fa8-170">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-170">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="f3fa8-171">Speichern Sie die Datei unter dem Dateinamen SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-171">Save the file as SampleUpdateSchema.xml.</span></span>  
  
3.  <span data-ttu-id="f3fa8-172">Kopieren Sie die oben stehende Updategramvorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-172">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="f3fa8-173">Speichern Sie die Datei unter dem Namen SampleUpdategram.xml im gleichen Verzeichnis, in dem Sie SampleUpdateSchema.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-173">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
     <span data-ttu-id="f3fa8-174">Der für das Zuordnungschema (SampleUpdateSchema.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-174">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="f3fa8-175">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f3fa8-175">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
4.  <span data-ttu-id="f3fa8-176">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f3fa8-176">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="f3fa8-177">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="f3fa8-177">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3fa8-178">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3fa8-178">See Also</span></span>  
 [<span data-ttu-id="f3fa8-179">Sicherheitsüberlegungen zu Update grams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f3fa8-179">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
