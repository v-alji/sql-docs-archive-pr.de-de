---
title: 'Erstellen konstanter Elemente mithilfe von SQL: is-constant (SQLXML 4,0) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- element does not map [SQLXML]
- sql:is-constant
- XSD schemas [SQLXML], constant elements
- element mapping [SQLXML], constant elements
- is-constant annotation
- constant elements [SQLXML]
- annotated XSD schemas, constant elements
ms.assetid: 940eea1b-54f5-445f-b844-c894d9f3941b
author: rothja
ms.author: jroth
ms.openlocfilehash: 8deedd8547d6bc3f0154eedb889ad908750f071a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717626"
---
# <a name="creating-constant-elements-using-sqlis-constant-sqlxml-40"></a><span data-ttu-id="59cec-102">Erstellen von 'constant'-Elementen unter Verwendung von sql:is-constant (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="59cec-102">Creating Constant Elements Using sql:is-constant (SQLXML 4.0)</span></span>
  <span data-ttu-id="59cec-103">Zum Angeben eines konstanten Elements, d. h. eines Elements im XSD-Schema, das keiner Datenbanktabelle oder-Spalte zugeordnet ist, können Sie die-Anmerkung verwenden `sql:is-constant` .</span><span class="sxs-lookup"><span data-stu-id="59cec-103">To specify a constant element-that is, an element in the XSD schema that does not map to any database table or column-you can use the `sql:is-constant` annotation.</span></span> <span data-ttu-id="59cec-104">Diese Anmerkung akzeptiert einen booleschen Wert (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="59cec-104">This annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="59cec-105">Zulässig sind die Werte 0, 1, true und false.</span><span class="sxs-lookup"><span data-stu-id="59cec-105">The acceptable values are 0, 1, true, and false.</span></span> <span data-ttu-id="59cec-106">Die `sql:is-constant`-Anmerkung kann für ein Element angegeben werden, das über keine Attribute verfügt.</span><span class="sxs-lookup"><span data-stu-id="59cec-106">The `sql:is-constant` annotation can be specified on an element that does not have any attributes.</span></span> <span data-ttu-id="59cec-107">Wenn sie für ein Element mit dem Wert true (oder 1) festgelegt ist, wird dieses Element nicht der Datenbank zugeordnet, aber dennoch im XML-Dokument angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59cec-107">If it is specified on an element with the value true (or 1), that element is not mapped to the database but still appears in the XML document.</span></span>  
  
 <span data-ttu-id="59cec-108">Die `sql:is-constant`-Anmerkung kann zu folgenden Zwecken verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="59cec-108">The `sql:is-constant` annotation can be used for:</span></span>  
  
-   <span data-ttu-id="59cec-109">Hinzufügen eines Elements der obersten Ebene zum XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="59cec-109">Adding a top-level element to the XML document.</span></span> <span data-ttu-id="59cec-110">XML erfordert ein einzelnes Element (Stammelement) der obersten Ebene für das Dokument.</span><span class="sxs-lookup"><span data-stu-id="59cec-110">XML requires a single top-level element (root element) for the document.</span></span>  
  
-   <span data-ttu-id="59cec-111">Erstellen von Container Elementen, z **\<Orders>** . b. ein Element, das alle Bestellungen umschließt.</span><span class="sxs-lookup"><span data-stu-id="59cec-111">Creating container elements, such as an **\<Orders>** element that wraps all orders.</span></span>  
  
 <span data-ttu-id="59cec-112">Die-Anmerkung `sql:is-constant` kann einem-Element hinzugefügt werden **\<complexType>** .</span><span class="sxs-lookup"><span data-stu-id="59cec-112">The `sql:is-constant` annotation can be added to a **\<complexType>** element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="59cec-113">Beispiele</span><span class="sxs-lookup"><span data-stu-id="59cec-113">Examples</span></span>  
 <span data-ttu-id="59cec-114">Es müssen bestimmte Anforderungen erfüllt sein, damit aus den folgenden Beispielen funktionierende Beispiele erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="59cec-114">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="59cec-115">Weitere Informationen finden Sie unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="59cec-115">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlis-constant-to-add-a-container-element"></a><span data-ttu-id="59cec-116">A.</span><span class="sxs-lookup"><span data-stu-id="59cec-116">A.</span></span> <span data-ttu-id="59cec-117">Angeben von "sql:is-constant" zum Hinzufügen eines Containerelements</span><span class="sxs-lookup"><span data-stu-id="59cec-117">Specifying sql:is-constant to add a container element</span></span>  
 <span data-ttu-id="59cec-118">In diesem mit Anmerkungen versehene XSD-Schema **\<CustomerOrders>** wird als konstantes Element definiert, indem das- `sql:is-constant` Attribut mit einem Wert von 1 angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="59cec-118">In this annotated XSD schema, **\<CustomerOrders>** is defined as a constant element by specifying the `sql:is-constant` attribute with a value of 1.</span></span> <span data-ttu-id="59cec-119">Daher **\<CustomerOrders>** ist keiner Datenbanktabelle oder-Spalte zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="59cec-119">Therefore, **\<CustomerOrders>** is not mapped to any database table or column.</span></span> <span data-ttu-id="59cec-120">Dieses Konstante Element besteht aus den untergeordneten- **\<Order>** Elementen.</span><span class="sxs-lookup"><span data-stu-id="59cec-120">This constant element consists of the **\<Order>** child elements.</span></span>  
  
 <span data-ttu-id="59cec-121">Obwohl **\<CustomerOrders>** keiner Datenbanktabelle oder-Spalte zugeordnet ist, wird Sie weiterhin im resultierenden XML-Code als Containerelement angezeigt, das die untergeordneten **\<Order>** Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="59cec-121">Although **\<CustomerOrders>** does not map to any database table or column, it still appears in the resulting XML as a container element containing the **\<Order>** child elements.</span></span>  
  
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
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="CustomerOrders" sql:is-constant="1" >  
          <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"  
                           sql:relationship="CustOrders"   
                           maxOccurs="unbounded" >  
                <xsd:complexType>  
                   <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                   <xsd:attribute name="OrderDate" type="xsd:date" />  
                   <xsd:attribute name="CustomerID" type="xsd:string" />  
                </xsd:complexType>  
              </xsd:element>  
            </xsd:sequence>  
           </xsd:complexType>  
          </xsd:element>  
         </xsd:sequence>  
          <xsd:attribute name="CustomerID" type="xsd:string" />  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="59cec-122">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="59cec-122">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="59cec-123">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="59cec-123">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="59cec-124">Speichern Sie die Datei unter dem Dateinamen isConstant.xml.</span><span class="sxs-lookup"><span data-stu-id="59cec-124">Save the file as isConstant.xml.</span></span>  
  
2.  <span data-ttu-id="59cec-125">Kopieren Sie die folgende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="59cec-125">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="59cec-126">Speichern Sie die Datei unter dem Namen isConstantT.xml im gleichen Verzeichnis, in dem Sie  isConstant.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="59cec-126">Save the file as isConstantT.xml in the same directory where you saved isConstant.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="isConstant.xml">  
            Customer[@CustomerID=1]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="59cec-127">Der für das Zuordnungsschema (isConstant.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="59cec-127">The directory path specified for the mapping schema (isConstant.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="59cec-128">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="59cec-128">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\isConstant.xml"  
    ```  
  
3.  <span data-ttu-id="59cec-129">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="59cec-129">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="59cec-130">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="59cec-130">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="59cec-131">Im Folgenden wird ein Teil des Resultsets aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="59cec-131">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
<Customer CustomerID="1">   
  <CustomerOrders>   
    <Order SalesOrderID="43860" OrderDate="2001-08-01" CustomerID="1" />   
    <Order SalesOrderID="44501" OrderDate="2001-11-01" CustomerID="1" />   
    <Order SalesOrderID="45283" OrderDate="2002-02-01" CustomerID="1" />   
    <Order SalesOrderID="46042" OrderDate="2002-05-01" CustomerID="1" />   
    ...  
  </CustomerOrders>   
</Customer>   
</ROOT>  
```  
  
  
