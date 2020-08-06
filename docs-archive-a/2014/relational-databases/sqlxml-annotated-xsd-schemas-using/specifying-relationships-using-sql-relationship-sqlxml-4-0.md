---
title: "Angeben von Beziehungen mit ' SQL: Relationship ' (SQLXML 4,0) | Microsoft-Dokumentation"
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREFS relationships [SQLXML]
- parent attribute [SQLXML]
- element relationships [SQLXML]
- multiple element relationships
- attribute relationships [SQLXML]
- sql:relationship
- relationship chains [SQLXML]
- IDREF relationships [SQLXML]
- parent-child relationships [SQLXML]
- relationship annotation
- XSD schemas [SQLXML], relationships
- annotated XSD schemas, relationships
- relationships [SQLXML], specifying
- unnamed relationships
- ID relationships [SQLXML]
- hierarchical relationships [SQLXML]
- named relationships [SQLXML]
ms.assetid: 98820afa-74e1-4e62-b336-6111a3dede4c
author: rothja
ms.author: jroth
ms.openlocfilehash: 42c703de9d564580eb0baa1349a45b193109c87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617898"
---
# <a name="specifying-relationships-using-sqlrelationship-sqlxml-40"></a><span data-ttu-id="1e041-102">Angeben von Beziehungen mit 'sql:relationship' (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="1e041-102">Specifying Relationships Using sql:relationship (SQLXML 4.0)</span></span>
  <span data-ttu-id="1e041-103">Die Elemente in einem XML-Dokument können in Beziehung gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="1e041-103">The elements in an XML document can be related.</span></span> <span data-ttu-id="1e041-104">Die Elemente können hierarchisch geschachtelt sein, und es können ID-, IDREF- oder IDREFS-Beziehungen zwischen den Elementen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1e041-104">The elements can be nested hierarchically, and ID, IDREF, or IDREFS relationships can be specified between the elements.</span></span>  
  
 <span data-ttu-id="1e041-105">In einem XSD-Schema enthält beispielsweise ein-Element untergeordnete- **\<Customer>** **\<Order>** Elemente.</span><span class="sxs-lookup"><span data-stu-id="1e041-105">For example, in an XSD schema, a **\<Customer>** element contains **\<Order>** child elements.</span></span> <span data-ttu-id="1e041-106">Wenn das Schema der AdventureWorks-Datenbank zugeordnet ist, wird das **\<Customer>** -Element der Sales. Customer-Tabelle zugeordnet, und das-Element wird der **\<Order>** Sales. SalesOrderHeader-Tabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1e041-106">When the schema is mapped to the AdventureWorks database, the **\<Customer>** element maps to the Sales.Customer table and the **\<Order>** element maps to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="1e041-107">Da Kunden Bestellungen aufgeben, stehen die zugrunde liegenden Tabellen Sales.Customer und Sales.SalesOrderHeader in Beziehung,.</span><span class="sxs-lookup"><span data-stu-id="1e041-107">These underlying tables, Sales.Customer and Sales.SalesOrderHeader, are related because customers place orders.</span></span> <span data-ttu-id="1e041-108">CustomerID in der Sales.SalesOrderHeader-Tabelle ist ein Fremdschlüssel, der auf den Primärschlüssel CustomerID in der Sales.Customer-Tabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="1e041-108">The CustomerID in the Sales.SalesOrderHeader table is a foreign key referring to the CustomerID primary key in the Sales.Customer table.</span></span> <span data-ttu-id="1e041-109">Sie können diese Beziehungen zwischen der Zuordnung von Schema Elementen mithilfe der-Anmerkung herstellen `sql:relationship` .</span><span class="sxs-lookup"><span data-stu-id="1e041-109">You can establish these relationships among mapping schema elements by using the `sql:relationship` annotation.</span></span>  
  
 <span data-ttu-id="1e041-110">In dem mit Anmerkungen versehenen XSD-Schema wird die `sql:relationship`-Anmerkung verwendet, um die Elemente des Schemas hierarchisch zu schachteln. Dies geschieht basierend auf der Primärschlüssel- und Fremdschlüsselbeziehung zwischen den zugrunde liegenden Tabellen, denen die Elemente zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1e041-110">In the annotated XSD schema, the `sql:relationship` annotation is used to nest the schema elements hierarchically, on the basis of primary key and foreign key relationships among the underlying tables to which the elements map.</span></span> <span data-ttu-id="1e041-111">Wenn Sie die-Anmerkung angeben `sql:relationship` , müssen Sie Folgendes identifizieren:</span><span class="sxs-lookup"><span data-stu-id="1e041-111">In specifying the `sql:relationship` annotation, you must identify the following:</span></span>  
  
-   <span data-ttu-id="1e041-112">Die übergeordnete Tabelle (Sales.Customer) und die untergeordnete Tabelle (Sales.SalesOrderHeader).</span><span class="sxs-lookup"><span data-stu-id="1e041-112">The parent table (Sales.Customer) and the child table (Sales.SalesOrderHeader).</span></span>  
  
-   <span data-ttu-id="1e041-113">Die Spalte oder Spalten, die das Verhältnis zwischen übergeordneten und untergeordneten Tabellen festlegen.</span><span class="sxs-lookup"><span data-stu-id="1e041-113">The column or columns that compose the relationship between the parent and child tables.</span></span> <span data-ttu-id="1e041-114">Beispiel: die Spalte CustomerID, die sowohl in übergeordneten als auch in untergeordneten Tabellen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1e041-114">For example, the CustomerID column, which appears in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="1e041-115">Diese Informationen dienen dazu, die richtige Hierarchie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e041-115">This information is used to generate the proper hierarchy.</span></span>  
  
 <span data-ttu-id="1e041-116">Die folgenden Attribute werden in der `sql:relationship`-Anmerkung festgelegt, um die Tabellenamen und die erforderlichen Joininformationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1e041-116">To provide the table names and the necessary join information, the following attributes are specified on the `sql:relationship` annotation.</span></span> <span data-ttu-id="1e041-117">Diese Attribute sind nur mit dem- **\<sql:relationship>** Element gültig:</span><span class="sxs-lookup"><span data-stu-id="1e041-117">These attributes are valid only with the **\<sql:relationship>** element:</span></span>  
  
 <span data-ttu-id="1e041-118">**Name**</span><span class="sxs-lookup"><span data-stu-id="1e041-118">**Name**</span></span>  
 <span data-ttu-id="1e041-119">Gibt den eindeutigen Namen der Beziehung an.</span><span class="sxs-lookup"><span data-stu-id="1e041-119">Specifies the unique name of the relationship.</span></span>  
  
 <span data-ttu-id="1e041-120">**Parent**</span><span class="sxs-lookup"><span data-stu-id="1e041-120">**Parent**</span></span>  
 <span data-ttu-id="1e041-121">Gibt die übergeordnete Beziehung (Tabelle) an.</span><span class="sxs-lookup"><span data-stu-id="1e041-121">Specifies the parent relation (table).</span></span> <span data-ttu-id="1e041-122">Dieses Attribut ist optional. Wird es nicht angegeben, wird der Name der übergeordneten Tabelle aus den Informationen in der untergeordneten Hierarchie des Dokuments abgerufen.</span><span class="sxs-lookup"><span data-stu-id="1e041-122">This is an optional attribute; if the attribute is not specified, the parent table name is obtained from information in the child hierarchy in the document.</span></span> <span data-ttu-id="1e041-123">Wenn das Schema zwei über-/unterordnungshierarchien angibt, die dieselben **\<sql:relationship>** , aber unterschiedliche übergeordnete Elemente verwenden, geben Sie das übergeordnete Attribut in nicht an **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="1e041-123">If the schema specifies two parent-child hierarchies that use the same **\<sql:relationship>** but different parent elements, you do not specify the parent attribute in **\<sql:relationship>**.</span></span> <span data-ttu-id="1e041-124">Diese Informationen werden aus der Hierarchie im Schema abgerufen.</span><span class="sxs-lookup"><span data-stu-id="1e041-124">This information is obtained from the hierarchy in the schema.</span></span>  
  
 <span data-ttu-id="1e041-125">**parent-key**</span><span class="sxs-lookup"><span data-stu-id="1e041-125">**parent-key**</span></span>  
 <span data-ttu-id="1e041-126">Gibt den übergeordneten Schlüssel des übergeordneten Elements an.</span><span class="sxs-lookup"><span data-stu-id="1e041-126">Specifies the parent key of the parent.</span></span> <span data-ttu-id="1e041-127">Wenn der übergeordnete Schlüssel aus mehreren Spalten besteht, werden Werte mit einer Leerstelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="1e041-127">If the parent key is composed of multiple columns, values are specified with a space between them.</span></span> <span data-ttu-id="1e041-128">Es besteht eine positionelle Zuordnung zwischen den Werten, die für den mehrspaltigen Schlüssel und für den entsprechenden untergeordneten Schlüssel festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="1e041-128">There is a positional mapping between the values that are specified for the multicolumn key and for the corresponding child key.</span></span>  
  
 <span data-ttu-id="1e041-129">**Idee**</span><span class="sxs-lookup"><span data-stu-id="1e041-129">**Child**</span></span>  
 <span data-ttu-id="1e041-130">Gibt die untergeordnete Beziehung (Tabelle) an.</span><span class="sxs-lookup"><span data-stu-id="1e041-130">Specifies the child relation (table).</span></span>  
  
 <span data-ttu-id="1e041-131">**child-key**</span><span class="sxs-lookup"><span data-stu-id="1e041-131">**child-key**</span></span>  
 <span data-ttu-id="1e041-132">Gibt den untergeordneten Schlüssel im untergeordneten Element an, das im übergeordnetem Element auf den übergeordneten Schlüssel verweist.</span><span class="sxs-lookup"><span data-stu-id="1e041-132">Specifies the child key in the child referring to parent-key in parent.</span></span> <span data-ttu-id="1e041-133">Wenn der untergeordnete Schlüssel aus mehreren Attributen (Spalten) besteht, werden Werte des untergeordneten Schlüssels mit einer Leerstelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="1e041-133">If the child key is composed of multiple attributes (columns), the child-key values are specified with a space between them.</span></span> <span data-ttu-id="1e041-134">Es besteht eine positionelle Zuordnung zwischen den Werten, die für den mehrspaltigen Schlüssel und für den entsprechenden übergeordneten Schlüssel festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="1e041-134">There is a positional mapping between the values that are specified for the multicolumn key and for the corresponding parent key.</span></span>  
  
 <span data-ttu-id="1e041-135">**Umgekehrt**</span><span class="sxs-lookup"><span data-stu-id="1e041-135">**Inverse**</span></span>  
 <span data-ttu-id="1e041-136">Dieses Attribut, das für angegeben **\<sql:relationship>** wurde, wird von Update grams verwendet.</span><span class="sxs-lookup"><span data-stu-id="1e041-136">This attribute specified on **\<sql:relationship>** is used by updategrams.</span></span> <span data-ttu-id="1e041-137">Weitere Informationen finden Sie unter [angeben des SQL: inverse-Attributs für SQL: Relationship](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="1e041-137">For more information, see [Specifying the sql:inverse Attribute on sql:relationship](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="1e041-138">Die `sql:key-fields` -Anmerkung muss in einem Element angegeben werden, das ein untergeordnetes Element enthält, das einen **\<sql:relationship>** zwischen dem-Element und dem untergeordneten-Element definiert hat und nicht den Primärschlüssel der im übergeordneten Element angegebenen Tabelle bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1e041-138">The `sql:key-fields` annotation must be specified in an element that contains a child element, that has a **\<sql:relationship>** defined between the element and the child, and that does not provide the primary key of the table specified in the parent element.</span></span> <span data-ttu-id="1e041-139">Auch wenn das Schema nicht angibt **\<sql:relationship>** , müssen Sie angeben, `sql:key-fields` um die richtige Hierarchie zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1e041-139">Even if the schema does not specify **\<sql:relationship>**, you must specify `sql:key-fields` to produce the proper hierarchy.</span></span> <span data-ttu-id="1e041-140">Weitere Informationen finden Sie unter [Identifizieren von Schlüssel Spalten mithilfe von SQL: key-fields](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="1e041-140">For more information, see [Identifying Key Columns by Using sql:key-fields](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="1e041-141">Um eine ordnungsgemäße Schachtelung im Ergebnis zu schaffen, wird empfohlen, dass Sie `sql:key-fields` in allen Schemas angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1e041-141">To produce proper nesting in the result, it is recommended that `sql:key-fields` are specified in all schemas.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1e041-142">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1e041-142">Examples</span></span>  
 <span data-ttu-id="1e041-143">Es müssen bestimmte Anforderungen erfüllt sein, damit aus den folgenden Beispielen funktionierende Beispiele erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="1e041-143">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="1e041-144">Weitere Informationen finden Sie unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="1e041-144">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlrelationship-annotation-on-an-element"></a><span data-ttu-id="1e041-145">A.</span><span class="sxs-lookup"><span data-stu-id="1e041-145">A.</span></span> <span data-ttu-id="1e041-146">Angeben der sql:relationship-Anmerkung für ein Element</span><span class="sxs-lookup"><span data-stu-id="1e041-146">Specifying the sql:relationship annotation on an element</span></span>  
 <span data-ttu-id="1e041-147">Das folgende mit Anmerkungen versehene XSD-Schema enthält die **\<Customer>** **\<Order>** Elemente und.</span><span class="sxs-lookup"><span data-stu-id="1e041-147">The following annotated XSD schema includes **\<Customer>** and **\<Order>** elements.</span></span> <span data-ttu-id="1e041-148">Das- **\<Order>** Element ist ein untergeordnetes Element des- **\<Customer>** Elements.</span><span class="sxs-lookup"><span data-stu-id="1e041-148">The **\<Order>** element is a child element of the **\<Customer>** element.</span></span>  
  
 <span data-ttu-id="1e041-149">Im Schema wird die-Anmerkung `sql:relationship` für das untergeordnete- **\<Order>** Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="1e041-149">In the schema, the `sql:relationship` annotation is specified on the **\<Order>** child element.</span></span> <span data-ttu-id="1e041-150">Die Beziehung selbst wird im- **\<xsd:appinfo>** Element definiert.</span><span class="sxs-lookup"><span data-stu-id="1e041-150">The relationship itself is defined in the **\<xsd:appinfo>** element.</span></span>  
  
 <span data-ttu-id="1e041-151">Das- **\<relationship>** Element identifiziert CustomerID in der Sales. SalesOrderHeader-Tabelle als Fremdschlüssel, der auf den CustomerID-Primärschlüssel in der Sales. Customer-Tabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="1e041-151">The **\<relationship>** element identifies CustomerID in the Sales.SalesOrderHeader table as a foreign key that refers to the CustomerID primary key in the Sales.Customer table.</span></span> <span data-ttu-id="1e041-152">Daher werden Aufträge, die zu einem Kunden gehören, als untergeordnetes Element dieses **\<Customer>** Elements angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e041-152">Therefore, orders that belong to a customer appear as a child element of that **\<Customer>** element.</span></span>  
  
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
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                    sql:relationship="CustOrders" >  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="1e041-153">Das vorherige Schema verwendet eine benannte Beziehung.</span><span class="sxs-lookup"><span data-stu-id="1e041-153">The previous schema uses a named relationship.</span></span> <span data-ttu-id="1e041-154">Sie können auch eine unbenannte Beziehung angeben.</span><span class="sxs-lookup"><span data-stu-id="1e041-154">You can also specify an unnamed relationship.</span></span> <span data-ttu-id="1e041-155">Das Ergebnis ist dasselbe.</span><span class="sxs-lookup"><span data-stu-id="1e041-155">The results are same.</span></span>  
  
 <span data-ttu-id="1e041-156">Dies ist das überarbeitete Schema, in dem eine unbenannte Beziehung angegeben wird:</span><span class="sxs-lookup"><span data-stu-id="1e041-156">This is the revised schema in which an unnamed relationship is specified:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer"  type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader">  
           <xsd:annotation>  
            <xsd:appinfo>  
              <sql:relationship   
                parent="Sales.Customer"  
                parent-key="CustomerID"  
                child="Sales.SalesOrderHeader"  
                child-key="CustomerID" />  
            </xsd:appinfo>  
           </xsd:annotation>  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="1e041-157">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="1e041-157">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="1e041-158">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="1e041-158">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="1e041-159">Speichern Sie die Datei unter dem Dateinamen sql-relationship.xml.</span><span class="sxs-lookup"><span data-stu-id="1e041-159">Save the file as sql-relationship.xml.</span></span>  
  
2.  <span data-ttu-id="1e041-160">Kopieren Sie die unten stehende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="1e041-160">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="1e041-161">Speichern Sie die Datei unter dem Namen sql-relationshipT.xml im gleichen Verzeichnis, in dem Sie sql-relationship.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="1e041-161">Save the file as sql-relationshipT.xml in the same directory where you saved sql-relationship.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sql-relationship.xml">  
            /Customer[@CustomerID=1]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="1e041-162">Der für das Zuordnungschema (sql-relationship.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="1e041-162">The directory path specified for the mapping schema (sql-relationship.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="1e041-163">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e041-163">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\sql-relationship.xml"  
    ```  
  
3.  <span data-ttu-id="1e041-164">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1e041-164">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="1e041-165">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="1e041-165">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="1e041-166">Im Folgenden wird das Resultset aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="1e041-166">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer CustomerID="1">   
    <Order OrderID="43860" CustomerID="1" />   
    <Order OrderID="44501" CustomerID="1" />   
    <Order OrderID="45283" CustomerID="1" />   
    <Order OrderID="46042" CustomerID="1" />   
  </Customer>   
</ROOT>  
```  
  
### <a name="b-specifying-a-relationship-chain"></a><span data-ttu-id="1e041-167">B.</span><span class="sxs-lookup"><span data-stu-id="1e041-167">B.</span></span> <span data-ttu-id="1e041-168">Angeben einer Beziehungskette</span><span class="sxs-lookup"><span data-stu-id="1e041-168">Specifying a relationship chain</span></span>  
 <span data-ttu-id="1e041-169">Angenommen, Sie verwenden das folgende XML-Dokument zur Abfrage von Daten aus der AdventureWorks-Datenbank:</span><span class="sxs-lookup"><span data-stu-id="1e041-169">For this example, assume that you want the following XML document using data obtained from the AdventureWorks database:</span></span>  
  
```  
<Order SalesOrderID="43659">  
  <Product Name="Mountain Bike Socks, M"/>   
  <Product Name="Sport-100 Helmet, Blue"/>  
  ...  
</Order>  
...  
```  
  
 <span data-ttu-id="1e041-170">Für jede Bestellung in der Sales. SalesOrderHeader-Tabelle weist das XML-Dokument ein- **\<Order>** Element auf.</span><span class="sxs-lookup"><span data-stu-id="1e041-170">For each order in the Sales.SalesOrderHeader table, the XML document has one **\<Order>** element.</span></span> <span data-ttu-id="1e041-171">Und jedes **\<Order>** Element verfügt über eine Liste untergeordneter **\<Product>** Elemente, eine für jedes in der Bestellung angeforderte Produkt.</span><span class="sxs-lookup"><span data-stu-id="1e041-171">And each **\<Order>** element has a list of **\<Product>** child elements, one for each product requested in the order.</span></span>  
  
 <span data-ttu-id="1e041-172">Zur Angabe eines XSD-Schemas, das diese Hierarchie erzeugt, müssen Sie zwei Beziehungen angeben: OrderOD und ODProduct.</span><span class="sxs-lookup"><span data-stu-id="1e041-172">To specify an XSD schema that will produce this hierarchy, you must specify two relationships: OrderOD and ODProduct.</span></span> <span data-ttu-id="1e041-173">Die OrderOD-Beziehung gibt die Über-/Unterordnungsbeziehung zwischen den Tabellen Sales.SalesOrderHeader und Sales.SalesOrderDetail an.</span><span class="sxs-lookup"><span data-stu-id="1e041-173">The OrderOD relationship specifies the parent-child relationship between the Sales.SalesOrderHeader and Sales.SalesOrderDetail tables.</span></span> <span data-ttu-id="1e041-174">Die ODProduct-Beziehung gibt die Beziehung zwischen den Tabellen Sales.SalesOrderDetail und Production.Product an.</span><span class="sxs-lookup"><span data-stu-id="1e041-174">The ODProduct relationship specifies the relationship between the Sales.SalesOrderDetail and Production.Product tables.</span></span>  
  
 <span data-ttu-id="1e041-175">Im folgenden Schema gibt die-Anmerkung `msdata:relationship` für das- **\<Product>** Element zwei Werte an: OrderOD und ODProduct.</span><span class="sxs-lookup"><span data-stu-id="1e041-175">In the following schema, the `msdata:relationship` annotation on the **\<Product>** element specifies two values: OrderOD and ODProduct.</span></span> <span data-ttu-id="1e041-176">Die Reihenfolge, in der diese Werte angegeben werden, spielt eine wichtige Rolle.</span><span class="sxs-lookup"><span data-stu-id="1e041-176">The order in which these values are specified is important.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <msdata:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  
    <msdata:relationship name="ODProduct"  
          parent="Sales.SalesOrderDetail"  
          parent-key="ProductID"  
          child="Production.Product"  
          child-key="ProductID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Order" msdata:relation="Sales.SalesOrderHeader"   
               msdata:key-fields="SalesOrderID" type="OrderType" />  
   <xsd:complexType name="OrderType" >  
     <xsd:sequence>  
        <xsd:element name="Product" msdata:relation="Production.Product"   
                     msdata:key-fields="ProductID"  
                     msdata:relationship="OrderOD ODProduct">  
          <xsd:complexType>  
             <xsd:attribute name="Name" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="SalesOrderID"   type="xsd:integer" />   
    </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="1e041-177">Statt eine benannte Beziehung anzugeben, können Sie eine anonyme Beziehung angeben.</span><span class="sxs-lookup"><span data-stu-id="1e041-177">Instead of specifying a named relationship, you can specify an anonymous relationship.</span></span> <span data-ttu-id="1e041-178">In diesem Fall wird der gesamte Inhalt von **\<annotation>** ... **\</annotation>** , der die beiden Beziehungen beschreibt, als untergeordnetes Element von angezeigt **\<Product>** .</span><span class="sxs-lookup"><span data-stu-id="1e041-178">In this case, the entire contents of **\<annotation>**...**\</annotation>**, which describes the two relationships, appear as a child element of **\<Product>**.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Order" msdata:relation="Sales.SalesOrderHeader"   
               msdata:key-fields="SalesOrderID" type="OrderType" />  
  
   <xsd:complexType name="OrderType" >  
     <xsd:sequence>  
        <xsd:element name="Product" msdata:relation="Production.Product"   
                     msdata:key-fields="ProductID" >  
         <xsd:annotation>  
          <xsd:appinfo>  
           <msdata:relationship   
               parent="Sales.SalesOrderHeader"  
               parent-key="SalesOrderID"  
               child="Sales.SalesOrderDetail"  
               child-key="SalesOrderID" />  
  
           <msdata:relationship   
               parent="Sales.SalesOrderDetail"  
               parent-key="ProductID"  
               child="Production.Product"  
               child-key="ProductID" />  
         </xsd:appinfo>  
       </xsd:annotation>  
       <xsd:complexType>  
          <xsd:attribute name="Name" type="xsd:string" />  
       </xsd:complexType>  
     </xsd:element>  
   </xsd:sequence>  
   <xsd:attribute name="SalesOrderID"   type="xsd:integer" />   
  </xsd:complexType>  
 </xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="1e041-179">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="1e041-179">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="1e041-180">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="1e041-180">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="1e041-181">Speichern Sie die Datei unter dem Dateinamen relationshipChain.xml.</span><span class="sxs-lookup"><span data-stu-id="1e041-181">Save the file as relationshipChain.xml.</span></span>  
  
2.  <span data-ttu-id="1e041-182">Kopieren Sie die unten stehende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="1e041-182">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="1e041-183">Speichern Sie die Datei unter dem Namen relationshipChainT.xml im gleichen Verzeichnis, in dem Sie relationshipChain.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="1e041-183">Save the file as relationshipChainT.xml in the same directory where you saved relationshipChain.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="relationshipChain.xml">  
            /Order  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="1e041-184">Der für das Zuordnungschema (relationshipChain.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="1e041-184">The directory path specified for the mapping schema (relationshipChain.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="1e041-185">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e041-185">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationshipChain.xml"  
    ```  
  
3.  <span data-ttu-id="1e041-186">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1e041-186">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="1e041-187">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="1e041-187">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="1e041-188">Im Folgenden wird das Resultset aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="1e041-188">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Order SalesOrderID="43659">  
    <Product Name="Mountain Bike Socks, M" />   
    <Product Name="Sport-100 Helmet, Blue" />   
    <Product Name="AWC Logo Cap" />   
    <Product Name="Long-Sleeve Logo Jersey, M" />   
    <Product Name="Long-Sleeve Logo Jersey, XL" />   
    ...  
  </Order>  
  ...  
</ROOT>  
```  
  
### <a name="c-specifying-the-relationship-annotation-on-an-attribute"></a><span data-ttu-id="1e041-189">C.</span><span class="sxs-lookup"><span data-stu-id="1e041-189">C.</span></span> <span data-ttu-id="1e041-190">Angeben der "relationship"-Anmerkung für ein Attribut</span><span class="sxs-lookup"><span data-stu-id="1e041-190">Specifying the relationship annotation on an attribute</span></span>  
 <span data-ttu-id="1e041-191">Das Schema in diesem Beispiel enthält ein \<Customer> -Element mit einem untergeordneten \<CustomerID> -Element und einem OrderIDList-Attribut des IDREFS-Typs.</span><span class="sxs-lookup"><span data-stu-id="1e041-191">The schema in this example includes a \<Customer> element with a \<CustomerID> child element and an OrderIDList attribute of IDREFS type.</span></span> <span data-ttu-id="1e041-192">Das- \<Customer> Element wird der Sales. Customer-Tabelle in der AdventureWorks-Datenbank zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1e041-192">The \<Customer> element maps to the Sales.Customer table in the AdventureWorks database.</span></span> <span data-ttu-id="1e041-193">Standardmäßig gilt der Gültigkeitsbereich dieser Zuordnung für alle untergeordneten Elemente oder Attribute, es sei denn, `sql:relation` wird für das untergeordnete Element oder Attribut angegeben. in diesem Fall muss die entsprechende Primärschlüssel-/Fremdschlüssel Beziehung mit dem-Element definiert werden \<relationship> .</span><span class="sxs-lookup"><span data-stu-id="1e041-193">By default, the scope of this mapping applies to all the child elements or attributes unless `sql:relation` is specified on the child element or attribute, in which case, the appropriate primary-key/foreign-key relationship must be defined using the \<relationship> element.</span></span> <span data-ttu-id="1e041-194">Das untergeordnete Element oder Attribut, welches die andere Tabelle mit der `relation`-Anmerkung angibt, muss ebenfalls die `relationship`-Anmerkung festlegen.</span><span class="sxs-lookup"><span data-stu-id="1e041-194">And the child element or attribute, which specifies the different table using the `relation` annotation, must also specify the `relationship` annotation.</span></span>  
  
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
     </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="CustomerID"   type="xsd:string" />   
     </xsd:sequence>  
     <xsd:attribute name="OrderIDList"   
                     type="xsd:IDREFS"   
                     sql:relation="Sales.SalesOrderHeader"   
                     sql:field="SalesOrderID"  
                     sql:relationship="CustOrders" >  
        </xsd:attribute>  
    </xsd:complexType>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="1e041-195">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="1e041-195">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="1e041-196">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="1e041-196">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="1e041-197">Speichern Sie die Datei unter dem Dateinamen relationship-on-attribute.xml.</span><span class="sxs-lookup"><span data-stu-id="1e041-197">Save the file as relationship-on-attribute.xml.</span></span>  
  
2.  <span data-ttu-id="1e041-198">Kopieren Sie die folgende Vorlage, und fügen Sie sie in eine Datei ein.</span><span class="sxs-lookup"><span data-stu-id="1e041-198">Copy the following template and paste it into a file.</span></span> <span data-ttu-id="1e041-199">Speichern Sie die Datei unter dem Namen relationship-on-attributeT.xml im gleichen Verzeichnis, in dem Sie relationship-on-attribute.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="1e041-199">Save the file as relationship-on-attributeT.xml in the same directory where you saved relationship-on-attribute.xml.</span></span> <span data-ttu-id="1e041-200">Die Abfrage in der Vorlage wählt einen Kunden mit der CustomerID des Werts 1 aus.</span><span class="sxs-lookup"><span data-stu-id="1e041-200">The query in the template selects a customer with the CustomerID of 1.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="relationship-on-attribute.xml">  
        /Customer[CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="1e041-201">Der für das Zuordnungschema (relationship-on-attribute.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="1e041-201">The directory path specified for the mapping schema (relationship-on-attribute.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="1e041-202">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e041-202">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-on-attribute.xml"  
    ```  
  
3.  <span data-ttu-id="1e041-203">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1e041-203">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="1e041-204">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="1e041-204">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="1e041-205">Im Folgenden wird das Resultset aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="1e041-205">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer OrderIDList="43860 44501 45283 46042">  
    <CustomerID>1</CustomerID>   
  </Customer>  
</ROOT>  
```  
  
### <a name="d-specifying-sqlrelationship-on-multiple-elements"></a><span data-ttu-id="1e041-206">D:</span><span class="sxs-lookup"><span data-stu-id="1e041-206">D.</span></span> <span data-ttu-id="1e041-207">Angeben von "sql:relationship" für mehrere Elemente</span><span class="sxs-lookup"><span data-stu-id="1e041-207">Specifying sql:relationship on multiple elements</span></span>  
 <span data-ttu-id="1e041-208">In diesem Beispiel enthält das mit Anmerkungen versehene XSD-Schema **\<Customer>** die **\<Order>** Elemente, und **\<OrderDetail>** .</span><span class="sxs-lookup"><span data-stu-id="1e041-208">In this example, the annotated XSD schema contains the **\<Customer>**, **\<Order>**, and **\<OrderDetail>** elements.</span></span>  
  
 <span data-ttu-id="1e041-209">Das- **\<Order>** Element ist ein untergeordnetes Element des- **\<Customer>** Elements.</span><span class="sxs-lookup"><span data-stu-id="1e041-209">The **\<Order>** element is a child element of the **\<Customer>** element.</span></span> <span data-ttu-id="1e041-210">**\<sql:relationship>** wird für das untergeordnete- **\<Order>** Element angegeben. aus diesem Grund werden Bestellungen eines Kunden als untergeordnete Elemente von angezeigt **\<Customer>** .</span><span class="sxs-lookup"><span data-stu-id="1e041-210">**\<sql:relationship>** is specified on the **\<Order>** child element; therefore, orders that belong to a customer appear as child elements of **\<Customer>**.</span></span>  
  
 <span data-ttu-id="1e041-211">Das- **\<Order>** Element enthält das untergeordnete- **\<OrderDetail>** Element.</span><span class="sxs-lookup"><span data-stu-id="1e041-211">The **\<Order>** element includes the **\<OrderDetail>** child element.</span></span> <span data-ttu-id="1e041-212">**\<sql:relationship>** wird für das untergeordnete- **\<OrderDetail>** Element angegeben, sodass die Bestelldetails für eine Bestellung als untergeordnete Elemente dieses- **\<Order>** Elements angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1e041-212">**\<sql:relationship>** is specified on **\<OrderDetail>** child element, so the order details that pertain to an order appear as child elements of that **\<Order>** element.</span></span>  
  
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
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="OrderDate" type="xsd:date" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="CustomerID" type="xsd:string" />  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="1e041-213">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="1e041-213">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="1e041-214">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="1e041-214">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="1e041-215">Speichern Sie die Datei unter dem Dateinamen relationship-multiple-elements.xml.</span><span class="sxs-lookup"><span data-stu-id="1e041-215">Save the file as relationship-multiple-elements.xml.</span></span>  
  
2.  <span data-ttu-id="1e041-216">Kopieren Sie die folgende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="1e041-216">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="1e041-217">Speichern Sie die Datei unter dem Namen relationship-multiple-elementsT.xml im gleichen Verzeichnis, in dem Sie relationship-multiple-elements gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="1e041-217">Save the file as relationship-multiple-elementsT.xml in the same directory where you saved relationship-multiple-elements.xml.</span></span> <span data-ttu-id="1e041-218">Die Abfrage in der Vorlage gibt die Bestellinformationen für einen Kunden mit der CustomerID des Werts 1 und der SalesOrderID des Werts 43860 zurück.</span><span class="sxs-lookup"><span data-stu-id="1e041-218">The query in the template returns order information for a customer with the CustomerID of 1 and SalesOrderID of 43860.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="relationship-multiple-elements.xml">  
        /Customer[@CustomerID=1]/Order[@SalesOrderID=43860]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="1e041-219">Der für das Zuordnungschema (relationship-multiple-elements.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="1e041-219">The directory path specified for the mapping schema (relationship-multiple-elements.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="1e041-220">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e041-220">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-multiple-elements.xml"  
    ```  
  
3.  <span data-ttu-id="1e041-221">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1e041-221">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="1e041-222">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="1e041-222">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="1e041-223">Im Folgenden wird das Resultset aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="1e041-223">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="43860" OrderDate="2001-08-01" CustomerID="1">  
     <OrderDetail SalesOrderID="43860" ProductID="761" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="770" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="758" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="765" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="732" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="762" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="738" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="768" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="753" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="729" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="763" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="756" OrderQty="1" />   
  </Order>  
</ROOT>  
```  
  
### <a name="e-specifying-the-sqlrelationship-without-the-parent-attribute"></a><span data-ttu-id="1e041-224">E.</span><span class="sxs-lookup"><span data-stu-id="1e041-224">E.</span></span> <span data-ttu-id="1e041-225">Angeben von \<sql:relationship> ohne das übergeordnete Attribut</span><span class="sxs-lookup"><span data-stu-id="1e041-225">Specifying the \<sql:relationship> without the parent attribute</span></span>  
 <span data-ttu-id="1e041-226">In diesem Beispiel wird das Angeben von **\<sql:relationship>** ohne das über **geordnete** Attribut veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1e041-226">This example illustrates specifying the **\<sql:relationship>** without the **parent** attribute.</span></span> <span data-ttu-id="1e041-227">Angenommen, es sind die folgenden Mitarbeitertabellen vorhanden:</span><span class="sxs-lookup"><span data-stu-id="1e041-227">For example, assume you have the following employee tables:</span></span>  
  
```  
Emp1(SalesPersonID, FirstName, LastName, ReportsTo)  
Emp2(SalesPersonID, FirstName, LastName, ReportsTo)  
```  
  
 <span data-ttu-id="1e041-228">In der folgenden XML-Sicht sind das **\<Emp1>** -Element und das- **\<Emp2>** Element den Tabellen Sales. Emp1 und Sales. Emp2 hinzu:</span><span class="sxs-lookup"><span data-stu-id="1e041-228">The following XML view has the **\<Emp1>** and **\<Emp2>** elements mapping to the Sales.Emp1 and Sales.Emp2 tables:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="EmpOrders"  
          parent-key="SalesPersonID"  
          child="Sales.SalesOrderHeader"  
          child-key="SalesPersonID" />  
     </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Emp1" sql:relation="Sales.Emp1" type="EmpType" />  
  <xsd:element name="Emp2" sql:relation="Sales.Emp2" type="EmpType" />  
   <xsd:complexType name="EmpType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"   
                     sql:relationship="EmpOrders" >  
          <xsd:complexType>  
             <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
             <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="SalesPersonID"   type="xsd:integer" />   
        <xsd:attribute name="LastName"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="1e041-229">Im Schema sind sowohl das **\<Emp1>** -Element als auch das- **\<Emp2>** Element vom Typ `EmpType` .</span><span class="sxs-lookup"><span data-stu-id="1e041-229">In the schema, both the **\<Emp1>** element and **\<Emp2>** element are of type `EmpType`.</span></span> <span data-ttu-id="1e041-230">Der Typ `EmpType` beschreibt ein **\<Order>** untergeordnetes Element und den entsprechenden **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="1e041-230">The type `EmpType` describes an **\<Order>** child element and the corresponding **\<sql:relationship>**.</span></span> <span data-ttu-id="1e041-231">In diesem Fall gibt es kein einzelnes übergeordnetes Element, das in **\<sql:relationship>** mithilfe des über **geordneten** Attributs identifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="1e041-231">In this case, there is no single parent that can be identified in **\<sql:relationship>** by using the **parent** attribute.</span></span> <span data-ttu-id="1e041-232">In diesem Fall geben Sie das über **geordnete** Attribut in nicht an **\<sql:relationship>** . die Informationen über das über **geordnete** Attribut werden aus der Hierarchie im Schema abgerufen.</span><span class="sxs-lookup"><span data-stu-id="1e041-232">In this situation, you don't specify the **parent** attribute in **\<sql:relationship>**; the **parent** attribute information is obtained from the hierarchy in the schema.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="1e041-233">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="1e041-233">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="1e041-234">Erstellen Sie diese Tabellen in der AdventureWorks-Datenbank:</span><span class="sxs-lookup"><span data-stu-id="1e041-234">Create these tables in the AdventureWorks database:</span></span>  
  
    ```  
    USE AdventureWorks  
    CREATE TABLE Sales.Emp1 (  
           SalesPersonID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    Go  
    CREATE TABLE Sales.Emp2 (  
           SalesPersonID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    Go  
    ```  
  
2.  <span data-ttu-id="1e041-235">Fügen Sie den Tabellen diese Beispieldaten hinzu:</span><span class="sxs-lookup"><span data-stu-id="1e041-235">Add this sample data in the tables:</span></span>  
  
    ```  
    INSERT INTO Sales.Emp1 values (279, 'Nancy', 'Devolio',NULL)  
    INSERT INTO Sales.Emp1 values (282, 'Andrew', 'Fuller',1)  
    INSERT INTO Sales.Emp1 values (276, 'Janet', 'Leverling',1)  
    INSERT INTO Sales.Emp2 values (277, 'Margaret', 'Peacock',3)  
    INSERT INTO Sales.Emp2 values (283, 'Steven', 'Devolio',4)  
    INSERT INTO Sales.Emp2 values (275, 'Nancy', 'Buchanan',5)  
    INSERT INTO Sales.Emp2 values (281, 'Michael', 'Suyama',6)  
    ```  
  
3.  <span data-ttu-id="1e041-236">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="1e041-236">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="1e041-237">Speichern Sie die Datei unter dem Dateinamen relationship-noparent.xml.</span><span class="sxs-lookup"><span data-stu-id="1e041-237">Save the file as relationship-noparent.xml.</span></span>  
  
4.  <span data-ttu-id="1e041-238">Kopieren Sie die folgende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="1e041-238">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="1e041-239">Speichern Sie die Datei unter dem Namen relationship-noparentT im gleichen Verzeichnis, in dem Sie relationship-noparent.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="1e041-239">Save the file as relationship-noparentT.xml in the same directory where you saved relationship-noparent.xml.</span></span> <span data-ttu-id="1e041-240">Die Abfrage in der Vorlage wählt alle \<Emp1> Elemente aus (daher ist das übergeordnete Element Emp1).</span><span class="sxs-lookup"><span data-stu-id="1e041-240">The query in the template selects all the \<Emp1> elements (therefore, the parent is Emp1).</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="relationship-noparent.xml">  
            /Emp1  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="1e041-241">Der für das Zuordnungschema (relationship-noparent.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="1e041-241">The directory path specified for the mapping schema (relationship-noparent.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="1e041-242">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e041-242">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-noparent.xml"  
    ```  
  
5.  <span data-ttu-id="1e041-243">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1e041-243">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="1e041-244">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="1e041-244">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="1e041-245">Im folgenden finden Sie ein partielles Resultset:</span><span class="sxs-lookup"><span data-stu-id="1e041-245">Here is a partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<Emp1 SalesPersonID="276" LastName="Leverling">  
  <Order SalesOrderID="43663" CustomerID="510" />   
  <Order SalesOrderID="43666" CustomerID="511" />   
  <Order SalesOrderID="43859" CustomerID="259" />  
  ...  
</Emp1>  
```  
  
  
