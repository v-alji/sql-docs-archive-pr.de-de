---
title: Angeben eines Ziel Namespace mit dem targetNamespace-Attribut (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces [SQLXML], annotated XSD schemas
- targetNamespace attribute
- XSD schemas [SQLXML], target namespaces
- annotated XSD schemas, target namespaces
- xsd:targetNamespace
- attributeFormDefault attribute
- elementFormDefault attribute
- target namespaces [SQLXML]
ms.assetid: f3df9877-6672-4444-8245-2670063c9310
author: rothja
ms.author: jroth
ms.openlocfilehash: 823bcbf7f4906a2e1d2ced1ff58b681c0ca41a8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621424"
---
# <a name="specifying-a-target-namespace-using-the-targetnamespace-attribute-sqlxml-40"></a><span data-ttu-id="10efb-102">Angeben eines Zielnamespaces mit dem 'targetNamespace'-Attribut (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="10efb-102">Specifying a Target Namespace Using the targetNamespace Attribute (SQLXML 4.0)</span></span>
  <span data-ttu-id="10efb-103">Beim Schreiben von XSD-Schemas können Sie das XSD- **targetNamespace** -Attribut verwenden, um einen Ziel Namespace anzugeben.</span><span class="sxs-lookup"><span data-stu-id="10efb-103">In writing XSD schemas, you can use the XSD **targetNamespace** attribute to specify a target namespace.</span></span> <span data-ttu-id="10efb-104">In diesem Thema wird beschrieben, wie das XSD-Attribut " **targetNamespace**", das **Element Form default**-Attribut und das **attributeFormDefault** -Attribut funktionieren, wie Sie sich auf die generierte XML-Instanz auswirken und wie XPath-Abfragen mit Namespaces angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="10efb-104">This topic describes how the XSD **targetNamespace**, **elementFormDefault**, and **attributeFormDefault** attributes work, how they affect the XML instance that is generated, and how XPath queries are specified with namespaces.</span></span>  
  
 <span data-ttu-id="10efb-105">Sie können das **xsd: targetNamespace** -Attribut verwenden, um Elemente und Attribute aus dem Standard Namespace in einen anderen Namespace zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="10efb-105">You can use the **xsd:targetNamespace** attribute to place elements and attributes from the default namespace into a different namespace.</span></span> <span data-ttu-id="10efb-106">Sie können auch festlegen, ob lokal deklarierte Elemente und Attribute des Schemas durch einen Namespace qualifiziert werden sollen, sei es explizit durch ein Präfix oder standardmäßig implizit.</span><span class="sxs-lookup"><span data-stu-id="10efb-106">You can also specify whether the locally declared elements and attributes of the schema should appear qualified by a namespace, either explicitly by using a prefix or implicitly by default.</span></span> <span data-ttu-id="10efb-107">Sie können die Attribute Element **Form default** und **attributeFormDefault** für das- **\<xsd:schema>** Element verwenden, um die Qualifizierung lokaler Elemente und Attribute global anzugeben, oder Sie können das **Form** -Attribut verwenden, um einzelne Elemente und Attribute separat anzugeben.</span><span class="sxs-lookup"><span data-stu-id="10efb-107">You can use the **elementFormDefault** and **attributeFormDefault** attributes on the **\<xsd:schema>** element to globally specify the qualification of local elements and attributes, or you can use the **form** attribute to specify individual elements and attributes separately.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="10efb-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="10efb-108">Examples</span></span>  
 <span data-ttu-id="10efb-109">Es müssen bestimmte Anforderungen erfüllt sein, damit aus den folgenden Beispielen funktionierende Beispiele erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="10efb-109">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="10efb-110">Weitere Informationen finden Sie unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="10efb-110">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-a-target-namespace"></a><span data-ttu-id="10efb-111">A.</span><span class="sxs-lookup"><span data-stu-id="10efb-111">A.</span></span> <span data-ttu-id="10efb-112">Angeben eines Zielnamespaces</span><span class="sxs-lookup"><span data-stu-id="10efb-112">Specifying a target namespace</span></span>  
 <span data-ttu-id="10efb-113">Das folgende XSD-Schema gibt einen Ziel Namespace mit dem **xsd: targetNamespace** -Attribut an.</span><span class="sxs-lookup"><span data-stu-id="10efb-113">The following XSD schema specifies a target namespace by using the **xsd:targetNamespace** attribute.</span></span> <span data-ttu-id="10efb-114">Das Schema legt auch die Attributwerte **Element Form default** und **attributeFormDefault** auf **"nicht qualifiziert"** (der Standardwert für diese Attribute) fest.</span><span class="sxs-lookup"><span data-stu-id="10efb-114">The schema also sets the **elementFormDefault** and **attributeFormDefault** attribute values to **"unqualified"** (the default value for these attributes).</span></span> <span data-ttu-id="10efb-115">Dies ist eine globale Deklaration und wirkt sich auf alle lokalen Elemente ( **\<Order>** im Schema) und Attribute (**CustomerID**, **ContactName**und **OrderID** im Schema) aus.</span><span class="sxs-lookup"><span data-stu-id="10efb-115">This is a global declaration and affects all the local elements (**\<Order>** in the schema) and attributes (**CustomerID**, **ContactName**, and **OrderID** in the schema).</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
            xmlns:CO="urn:MyNamespace"   
            targetNamespace="urn:MyNamespace" >  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer"   
               sql:relation="Sales.Customer"   
               type="CO:CustomerType" />  
  
  <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                     sql:relationship="CustOrders"  
                     type="CO:OrderType" />  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
        <xsd:attribute name="SalesPersonID"  type="xsd:string" />  
  </xsd:complexType>  
  <xsd:complexType name="OrderType" >  
     <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
     <xsd:attribute name="CustomerID" type="xsd:string" />  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="10efb-116">Im Schema:</span><span class="sxs-lookup"><span data-stu-id="10efb-116">In the schema:</span></span>  
  
-   <span data-ttu-id="10efb-117">Die Typdeklarationen **CustomerType** und **OrderType** sind global und sind daher im Ziel Namespace des Schemas enthalten.</span><span class="sxs-lookup"><span data-stu-id="10efb-117">The **CustomerType** and **OrderType** type declarations are global and, therefore, are included in the schema's target namespace.</span></span> <span data-ttu-id="10efb-118">Wenn auf diese Typen in der Deklaration des **\<Customer>** -Elements und seines untergeordneten Elements verwiesen wird **\<Order>** , wird daher ein Präfix angegeben, das dem Ziel Namespace zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="10efb-118">As a result, when these types are referenced in the declaration of **\<Customer>** element and its **\<Order>** child element, a prefix is specified that is associated with the target namespace.</span></span>  
  
-   <span data-ttu-id="10efb-119">Das- **\<Customer>** Element ist auch im Ziel Namespace des Schemas enthalten, da es sich um ein globales Element im Schema handelt.</span><span class="sxs-lookup"><span data-stu-id="10efb-119">The **\<Customer>** element is also included in the target namespace of the schema because it is a global element in the schema.</span></span>  
  
 <span data-ttu-id="10efb-120">Führen Sie die folgende XPath-Abfrage für das Schema aus:</span><span class="sxs-lookup"><span data-stu-id="10efb-120">Execute the following XPath query against the schema:</span></span>  
  
```  
(/CO:Customer[@CustomerID=1)   
```  
  
 <span data-ttu-id="10efb-121">Die XPath-Abfrage generiert dieses Instanzdokument (nur einige der Bestellungen werden angezeigt):</span><span class="sxs-lookup"><span data-stu-id="10efb-121">The XPath query generates this instance document (only a few of the orders are shown):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <y0:Customer xmlns:y0="urn:MyNamespace"   
      CustomerID="ALFKI" ContactName="Maria Anders">  
        <Order CustomerID="ALFKI" OrderID="10643" />   
        <Order CustomerID="ALFKI" OrderID="10692" />   
        ...  
  </y0:Customer>  
  </ROOT>  
```  
  
 <span data-ttu-id="10efb-122">Dieses Instanzdokument definiert den urn: MyNamespace-Namespace und ordnet ihm ein Präfix (y0) zu.</span><span class="sxs-lookup"><span data-stu-id="10efb-122">This instance document defines the urn:MyNamespace namespace and associates a prefix (y0) to it.</span></span> <span data-ttu-id="10efb-123">Das-Präfix wird nur auf das **\<Customer>** globale-Element angewendet.</span><span class="sxs-lookup"><span data-stu-id="10efb-123">The prefix is applied only to the **\<Customer>** global element.</span></span> <span data-ttu-id="10efb-124">(Das-Element ist Global, da es als untergeordnetes Element des- **\<xsd:schema>** Elements im Schema deklariert ist.)</span><span class="sxs-lookup"><span data-stu-id="10efb-124">(The element is global because it is declared as a child of **\<xsd:schema>** element in the schema.)</span></span>  
  
 <span data-ttu-id="10efb-125">Das-Präfix wird nicht auf die lokalen Elemente und Attribute angewendet, da der Wert der Attribute **Element Form default** und **attributeFormDefault** im Schema auf **"nicht qualifiziert"** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="10efb-125">The prefix is not applied to the local elements and attributes because the value of **elementFormDefault** and **attributeFormDefault** attributes is set to **"unqualified"** in the schema.</span></span> <span data-ttu-id="10efb-126">Beachten Sie, dass das- **\<Order>** Element lokal ist, da seine Deklaration als untergeordnetes Element des-Elements angezeigt wird **\<complexType>** , das das **\<CustomerType>** Element definiert.</span><span class="sxs-lookup"><span data-stu-id="10efb-126">Note that the **\<Order>** element is local because its declaration appears as a child of the **\<complexType>** element that defines the **\<CustomerType>** element.</span></span> <span data-ttu-id="10efb-127">Ebenso sind die Attribute (**CustomerID**, **OrderID**und **ContactName**) lokal und nicht global.</span><span class="sxs-lookup"><span data-stu-id="10efb-127">Similarly, the attributes (**CustomerID**, **OrderID**, and **ContactName**) are local, not global.</span></span>  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="10efb-128">So erstellen Sie ein funktionstüchtiges Beispiel für dieses Schema</span><span class="sxs-lookup"><span data-stu-id="10efb-128">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="10efb-129">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="10efb-129">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="10efb-130">Speichern Sie die Datei unter dem Dateinamen targetNameSpace.xml.</span><span class="sxs-lookup"><span data-stu-id="10efb-130">Save the file as targetNameSpace.xml.</span></span>  
  
2.  <span data-ttu-id="10efb-131">Kopieren Sie die folgende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="10efb-131">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="10efb-132">Speichern Sie die Datei unter dem Namen targetNameSpaceT.xml im gleichen Verzeichnis, in dem Sie targetNameSpace.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="10efb-132">Save the file as targetNameSpaceT.xml in the same directory where you saved targetNamespace.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="targetNamespace.xml"  
                       xmlns:CO="urn:MyNamespace" >  
        /CO:Customer[@CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="10efb-133">Die XPath-Abfrage in der Vorlage gibt das- **\<Customer>** Element für den Kunden mit dem CustomerID-Wert 1 zurück.</span><span class="sxs-lookup"><span data-stu-id="10efb-133">The XPath query in the template returns the **\<Customer>** element for the customer with a CustomerID of 1.</span></span> <span data-ttu-id="10efb-134">Beachten Sie, dass die XPath-Abfrage das Namespace-Präfix für das Element, nicht für das Attribut, in der Abfrage festlegt.</span><span class="sxs-lookup"><span data-stu-id="10efb-134">Note that the XPath query specifies the namespace prefix for the element in the query and not for the attribute.</span></span> <span data-ttu-id="10efb-135">(Lokale Attribute sind nicht qualifiziert, wie im Schema angegeben.)</span><span class="sxs-lookup"><span data-stu-id="10efb-135">(Local attributes are not qualified, as specified in the schema.)</span></span>  
  
     <span data-ttu-id="10efb-136">Der für das Zuordnungsschema (targetNameSpace.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="10efb-136">The directory path specified for the mapping schema (targetNamespace.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="10efb-137">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="10efb-137">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\targetNamepsace.xml"  
    ```  
  
3.  <span data-ttu-id="10efb-138">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="10efb-138">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="10efb-139">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="10efb-139">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="10efb-140">Wenn das Schema die Attribute **Element Form default** und **attributeFormDefault** mit dem Wert **"qualified"** angibt, werden für das Instanzdokument alle lokalen Elemente und Attribute qualifiziert.</span><span class="sxs-lookup"><span data-stu-id="10efb-140">If the schema specifies **elementFormDefault** and **attributeFormDefault** attributes with value **"qualified"**, the instance document will have all of the local elements and attributes qualified.</span></span> <span data-ttu-id="10efb-141">Sie können das vorherige Schema so ändern, dass diese Attribute im **\<xsd:schema>** -Element enthalten sind, und die Vorlage erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="10efb-141">You can change the previous schema to include these attributes in the **\<xsd:schema>** element and execute the template again.</span></span> <span data-ttu-id="10efb-142">Da die Attribute nun auch in der Instanz qualifiziert sind, ändert sich die XPath-Abfrage so, dass auch das Namespace-Präfix enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="10efb-142">Because the attributes are now also qualified in the instance, the XPath query will change to include the namespace prefix.</span></span>  
  
 <span data-ttu-id="10efb-143">Dies ist die geänderte XPath-Abfrage:</span><span class="sxs-lookup"><span data-stu-id="10efb-143">This is the revised XPath query:</span></span>  
  
```  
/CO:Customer[@CO:CustomerID=1]  
```  
  
 <span data-ttu-id="10efb-144">Dies ist das zurückgegebene XML-Dokument:</span><span class="sxs-lookup"><span data-stu-id="10efb-144">This is the XML document that is returned:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <y0:Customer xmlns:y0="urn:MyNamespace" CustomerID="1" SalesPersonID="280">  
      <Order SalesOrderID="43860" CustomerID="1" />   
      <Order SalesOrderID="44501" CustomerID="1" />   
      <Order SalesOrderID="45283" CustomerID="1" />   
      <Order SalesOrderID="46042" CustomerID="1" />   
   </y0:Customer>  
</ROOT>  
```  
  
  
