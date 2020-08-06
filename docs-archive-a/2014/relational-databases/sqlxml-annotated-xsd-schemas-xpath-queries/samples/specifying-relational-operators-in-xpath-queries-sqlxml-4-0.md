---
title: Angeben von relationalen Operatoren in XPath-Abfragen (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], relational operators
- relational operators [SQLXML]
- XPath operators [SQLXML]
- operators [SQLXML]
ms.assetid: 177a0eb2-11ef-4459-a317-485a433ee769
author: rothja
ms.author: jroth
ms.openlocfilehash: 50d59ebd3a776386c61f4c3a8a1e892d30981d1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608480"
---
# <a name="specifying-relational-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="ed58e-102">Angeben von relationalen Operatoren in XPath-Abfragen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ed58e-102">Specifying Relational Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="ed58e-103">In den folgenden Beispielen wird gezeigt, wie relationale Operatoren in XPath-Abfragen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ed58e-103">The following examples show how relational operators are specified in XPath queries.</span></span> <span data-ttu-id="ed58e-104">Die XPath-Abfragen in diesen Beispielen werden für das in SampleSchema1.xml enthaltene Zuordnungsschema angegeben.</span><span class="sxs-lookup"><span data-stu-id="ed58e-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="ed58e-105">Weitere Informationen zu diesem Beispiel Schema finden Sie unter [Beispiel: XSD-Schema mit Anmerkungen für XPath-Beispiele &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ed58e-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ed58e-106">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ed58e-106">Examples</span></span>  
  
### <a name="a-specify-relational-operator"></a><span data-ttu-id="ed58e-107">A.</span><span class="sxs-lookup"><span data-stu-id="ed58e-107">A.</span></span> <span data-ttu-id="ed58e-108">Angeben relationaler Operatoren</span><span class="sxs-lookup"><span data-stu-id="ed58e-108">Specify relational operator</span></span>  
 <span data-ttu-id="ed58e-109">Diese XPath-Abfrage gibt die untergeordneten Elemente des **\<Customer>** -Elements zurück, wobei der **CustomerID-** Attribut Wert "1" ist und alle untergeordneten **\<Order>** Elemente ein untergeordnetes Element **\<OrderDetail>** mit einem **OrderQty** -Attribut mit einem Wert größer als 3 enthalten:</span><span class="sxs-lookup"><span data-stu-id="ed58e-109">This XPath query returns the child elements of the **\<Customer>** element where the **CustomerID** attribute value is "1" and where any child **\<Order>** elements contain an **\<OrderDetail>** child with a **OrderQty** attribute with a value greater than 3:</span></span>  
  
```  
/child::Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
```  
  
 <span data-ttu-id="ed58e-110">Das in den Klammern angegebene Prädikat filtert die **\<Customer>** Elemente.</span><span class="sxs-lookup"><span data-stu-id="ed58e-110">The predicate specified in the brackets filters the **\<Customer>** elements.</span></span> <span data-ttu-id="ed58e-111">**\<Customer>** Es werden nur die Elemente zurückgegeben, für die mindestens ein untergeordnetes Element **\<OrderDetail>** mit einem OrderQty-Attribut Wert größer als 3 vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ed58e-111">Only the **\<Customer>** elements that have at least one **\<OrderDetail>** grandchild with a OrderQty attribute value greater than 3 are returned.</span></span>  
  
 <span data-ttu-id="ed58e-112">Die `child`-Achse ist die Standardachse.</span><span class="sxs-lookup"><span data-stu-id="ed58e-112">The `child` axis is the default.</span></span> <span data-ttu-id="ed58e-113">Daher kann die Abfrage wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="ed58e-113">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="ed58e-114">So testen Sie die XPath-Abfrage mit dem Zuordnungsschema</span><span class="sxs-lookup"><span data-stu-id="ed58e-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="ed58e-115">Kopieren Sie den [Beispiel Schema Code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) , und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="ed58e-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="ed58e-116">Speichern Sie die Datei unter dem Dateinamen SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="ed58e-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="ed58e-117">Erstellen Sie die folgende Vorlage (SpecifyRelationalA.xml), und speichern Sie sie in dem Verzeichnis, in dem SampleSchema1.xml gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="ed58e-117">Create the following template (SpecifyRelationalA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="ed58e-118">Der für das Zuordnungsschema (SampleSchema1.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="ed58e-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="ed58e-119">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ed58e-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="ed58e-120">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ed58e-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="ed58e-121">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ed58e-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="ed58e-122">Im Folgenden finden Sie das Resultset der Vorlagenausführung:</span><span class="sxs-lookup"><span data-stu-id="ed58e-122">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <OrderDetail ProductID="Prod-760" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-766" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-757" UnitPrice="1049.7528" OrderQty="4" UnitPriceDiscount="0" />   
</ROOT>  
```  
  
### <a name="b-specify-relational-operator-in-the-xpath-query-and-use-boolean-function-to-compare-the-result"></a><span data-ttu-id="ed58e-123">B.</span><span class="sxs-lookup"><span data-stu-id="ed58e-123">B.</span></span> <span data-ttu-id="ed58e-124">Angeben eines relationalen Operators in der XPath-Abfrage und Ergebnisvergleich mit boolescher Funktion</span><span class="sxs-lookup"><span data-stu-id="ed58e-124">Specify relational operator in the XPath query and use Boolean function to compare the result</span></span>  
 <span data-ttu-id="ed58e-125">Diese Abfrage gibt alle untergeordneten- **\<Order>** Elemente des Kontext Knotens zurück, die einen **SalesPersonID** -Attribut Wert aufweisen, der kleiner als 270 ist:</span><span class="sxs-lookup"><span data-stu-id="ed58e-125">This query returns all the **\<Order>** element children of the context node that have an **SalesPersonID** attribute value that is less than 270:</span></span>  
  
```  
/child::Customer/child::Order[(attribute::SalesPersonID < 270)=true()]  
```  
  
 <span data-ttu-id="ed58e-126">Es kann eine Abkürzung für die `attribute`-Achse (@) angegeben werden, und da die `child`-Achse die Standardachse ist, muss sie in der Abfrage nicht angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="ed58e-126">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer/Order[(@SalesPersonID < 270)=true()]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="ed58e-127">Wenn diese Abfrage in einer Vorlage angegeben ist, muss das < Zeichen Entität codiert sein, da das < Zeichen in einem XML-Dokument eine besondere Bedeutung hat.</span><span class="sxs-lookup"><span data-stu-id="ed58e-127">When this query is specified in a template, the < character must be entity encoded because the < character has special meaning in an XML document.</span></span> <span data-ttu-id="ed58e-128">Verwenden Sie in einer Vorlage, `<` um das < Zeichen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed58e-128">In a template, use `<` to specify the < character.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="ed58e-129">So testen Sie die XPath-Abfrage mit dem Zuordnungsschema</span><span class="sxs-lookup"><span data-stu-id="ed58e-129">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="ed58e-130">Kopieren Sie den [Beispiel Schema Code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) , und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="ed58e-130">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="ed58e-131">Speichern Sie die Datei unter dem Dateinamen SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="ed58e-131">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="ed58e-132">Erstellen Sie die folgende Vorlage (SpecifyRelationalB.xml), und speichern Sie sie in dem Verzeichnis, in dem SampleSchema1.xml gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="ed58e-132">Create the following template (SpecifyRelationalB.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="SampleSchema1.xml">  
            /Customer/Order[(@SalesPersonID<270)=true()]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="ed58e-133">Der für das Zuordnungsschema (SampleSchema1.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="ed58e-133">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="ed58e-134">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ed58e-134">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="ed58e-135">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ed58e-135">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="ed58e-136">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ed58e-136">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="ed58e-137">Im Folgenden finden Sie einen Auszug aus dem Resultset der Vorlagenausführung:</span><span class="sxs-lookup"><span data-stu-id="ed58e-137">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-46613" SalesPersonID="268"   
         OrderDate="2002-07-01T00:00:00"   
         DueDate="2002-07-13T00:00:00"   
         ShipDate="2002-07-08T00:00:00">  
    <OrderDetail ProductID="Prod-739" UnitPrice="917.9363"   
                 OrderQty="2" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-779" UnitPrice="1491.4221"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-825" UnitPrice="242.1391"   
                 OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
  <Order SalesOrderID="Ord-71919" SalesPersonID="268"  
         OrderDate="2004-06-01T00:00:00"   
         DueDate="2004-06-13T00:00:00"   
         ShipDate="2004-06-08T00:00:00">  
    <OrderDetail ProductID="Prod-961" UnitPrice="534.492"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-965" UnitPrice="534.492"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-966" UnitPrice="1716.5304"   
                 OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
  ...  
</ROOT>  
```  
  
  
