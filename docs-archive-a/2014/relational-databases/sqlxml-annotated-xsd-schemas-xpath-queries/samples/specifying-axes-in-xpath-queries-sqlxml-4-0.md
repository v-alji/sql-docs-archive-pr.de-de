---
title: Angeben von Achsen in XPath-Abfragen (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], axes
- context node [SQLXML]
- attribute axis [SQLXML]
- axis [SQLXML]
- child axis
- parent axis
- axes [SQLXML]
ms.assetid: d17b8278-da58-4576-95b4-7a92772566d8
author: rothja
ms.author: jroth
ms.openlocfilehash: f6f17404ea109bb0e687f9116b61025bbc411008
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608491"
---
# <a name="specifying-axes-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="817df-102">Angeben von Achsen in XPath-Abfragen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="817df-102">Specifying Axes in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="817df-103">In den folgenden Beispielen wird gezeigt, wie Achsen in XPath-Abfragen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="817df-103">The following examples show how axes are specified in XPath queries.</span></span>  
  
 <span data-ttu-id="817df-104">Die XPath-Abfragen in diesen Beispielen werden für das in SampleSchema1.xml enthaltene Zuordnungsschema angegeben.</span><span class="sxs-lookup"><span data-stu-id="817df-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="817df-105">Weitere Informationen zu diesem Beispiel Schema finden Sie unter [Beispiel: XSD-Schema mit Anmerkungen für XPath-Beispiele &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="817df-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="817df-106">Beispiele</span><span class="sxs-lookup"><span data-stu-id="817df-106">Examples</span></span>  
  
### <a name="a-retrieve-child-elements-of-the-context-node"></a><span data-ttu-id="817df-107">A.</span><span class="sxs-lookup"><span data-stu-id="817df-107">A.</span></span> <span data-ttu-id="817df-108">Abrufen von untergeordneten Elementen des Kontextknotens</span><span class="sxs-lookup"><span data-stu-id="817df-108">Retrieve child elements of the context node</span></span>  
 <span data-ttu-id="817df-109">Die folgende XPath-Abfrage wählt alle untergeordneten **\<Contact>** Elemente des Kontext Knotens aus:</span><span class="sxs-lookup"><span data-stu-id="817df-109">The following XPath query selects all the **\<Contact>** child elements of the context node:</span></span>  
  
```  
/child::Contact  
```  
  
 <span data-ttu-id="817df-110">In der Abfrage `child` ist die Achse und `Contact` ist der Knoten Test (true, wenn `Contact` ein- **\<element>** Knoten ist, da \<element> der primäre Knotentyp ist, der der Achse zugeordnet ist `child` ).</span><span class="sxs-lookup"><span data-stu-id="817df-110">In the query, `child` is the axis and `Contact` is the node test (TRUE if `Contact` is an **\<element>** node, because \<element> is the primary node type associated with the `child` axis).</span></span>  
  
 <span data-ttu-id="817df-111">Die `child`-Achse ist die Standardachse.</span><span class="sxs-lookup"><span data-stu-id="817df-111">The `child` axis is the default.</span></span> <span data-ttu-id="817df-112">Daher kann die Abfrage wie folgt geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="817df-112">Therefore, the query can be written as:</span></span>  
  
```  
/Contact  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="817df-113">So testen Sie die XPath-Abfrage mit dem Zuordnungsschema</span><span class="sxs-lookup"><span data-stu-id="817df-113">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="817df-114">Kopieren Sie den [Beispiel Schema Code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) , und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="817df-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="817df-115">Speichern Sie die Datei unter dem Dateinamen SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="817df-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="817df-116">Erstellen Sie die folgende Vorlage (XPathAxesSampleA.xml), und speichern Sie sie in dem Verzeichnis, in dem SampleSchema1.xml gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="817df-116">Create the following template (XPathAxesSampleA.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Contact  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="817df-117">Der für das Zuordnungsschema (SampleSchema1.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="817df-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="817df-118">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="817df-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="817df-119">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="817df-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="817df-120">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="817df-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="817df-121">Im Folgenden finden Sie einen Auszug aus dem Resultset der Vorlagenausführung:</span><span class="sxs-lookup"><span data-stu-id="817df-121">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Contact ContactID="1" LastName="Achong" FirstName="Gustavo" Title="Mr." />   
  <Contact ContactID="2" LastName="Abel" FirstName="Catherine" Title="Ms." />   
  <Contact ContactID="3" LastName="Abercrombie" FirstName="Kim" Title="Ms." />   
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />  
  ...  
</ROOT>  
```  
  
### <a name="b-retrieve-grandchildren-of-the-context-node"></a><span data-ttu-id="817df-122">B.</span><span class="sxs-lookup"><span data-stu-id="817df-122">B.</span></span> <span data-ttu-id="817df-123">Abrufen von untergeordneten Elementen zweiter Ordnung des Kontextknotens</span><span class="sxs-lookup"><span data-stu-id="817df-123">Retrieve grandchildren of the context node</span></span>  
 <span data-ttu-id="817df-124">Die folgende XPath-Abfrage wählt alle untergeordneten-Elemente der untergeordneten- **\<Order>** **\<Customer>** Elemente des Kontext Knotens aus:</span><span class="sxs-lookup"><span data-stu-id="817df-124">The following XPath query selects all the **\<Order>** element children of the **\<Customer>** element children of the context node:</span></span>  
  
```  
/child::Customer/child::Order  
```  
  
 <span data-ttu-id="817df-125">In der Abfrage `child` ist die Achse und `Customer` und `Order` sind die Knoten Tests (diese Knoten Tests sind true, wenn Customer und ORDER Knoten sind **\<element>** , da der **\<element>** Knoten der primäre Knoten für die- `child` Achse ist).</span><span class="sxs-lookup"><span data-stu-id="817df-125">In the query, `child` is the axis and `Customer` and `Order` are the node tests (these node tests are TRUE if Customer and Order are **\<element>** nodes, because the **\<element>** node is the primary node for the `child` axis).</span></span> <span data-ttu-id="817df-126">**\<Customer>** Die Knoten, die mit übereinstimmen, **\<Orders>** werden dem Ergebnis hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="817df-126">For each node matching **\<Customer>**, the nodes matching **\<Orders>** are added to the result.</span></span> <span data-ttu-id="817df-127">**\<Order>** Im Resultset wird nur zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="817df-127">Only **\<Order>** is returned in the result set.</span></span>  
  
 <span data-ttu-id="817df-128">Die `child`-Achse ist die Standardachse.</span><span class="sxs-lookup"><span data-stu-id="817df-128">The `child` axis is the default.</span></span> <span data-ttu-id="817df-129">Daher kann die Abfrage wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="817df-129">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer/Order  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="817df-130">So testen Sie die XPath-Abfrage mit dem Zuordnungsschema</span><span class="sxs-lookup"><span data-stu-id="817df-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="817df-131">Kopieren Sie den [Beispiel Schema Code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) , und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="817df-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="817df-132">Speichern Sie die Datei unter dem Dateinamen SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="817df-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="817df-133">Erstellen Sie die folgende Vorlage (XPathAxesSampleB.xml), und speichern Sie sie im folgenden Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="817df-133">Create the following template (XPathAxesSampleB.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer/Order  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="817df-134">Der für das Zuordnungsschema (SampleSchema1.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="817df-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="817df-135">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="817df-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="817df-136">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="817df-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="817df-137">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="817df-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="817df-138">Im Folgenden finden Sie einen Auszug aus dem Resultset der Vorlagenausführung:</span><span class="sxs-lookup"><span data-stu-id="817df-138">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
         OrderDate="2001-08-01T00:00:00"   
         DueDate="2001-08-13T00:00:00"   
         ShipDate="2001-08-08T00:00:00">  
  <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-761" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-762" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-765" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-768" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-770" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
   ...  
</ROOT>  
```  
  
 <span data-ttu-id="817df-139">Wenn die XPath-Abfrage als angegeben wird `Customer/Order/OrderDetail` , **\<Customer>** navigiert die Abfrage von jedem Knoten, der der Abfrage entspricht **\<Order>** .</span><span class="sxs-lookup"><span data-stu-id="817df-139">If the XPath query is specified as `Customer/Order/OrderDetail`, from each node matching **\<Customer>** the query navigates to its **\<Order>** elements.</span></span> <span data-ttu-id="817df-140">Und für jeden Knoten, der übereinstimmt **\<Order>** , fügt die Abfrage die Knoten dem **\<OrderDetail>** Ergebnis hinzu.</span><span class="sxs-lookup"><span data-stu-id="817df-140">And for each node matching **\<Order>**, the query adds the nodes **\<OrderDetail>** to the result.</span></span> <span data-ttu-id="817df-141">**\<OrderDetail>** Im Resultset wird nur zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="817df-141">Only **\<OrderDetail>** is returned in the result set.</span></span>  
  
### <a name="c-use--to-specify-the-parent-axis"></a><span data-ttu-id="817df-142">C.</span><span class="sxs-lookup"><span data-stu-id="817df-142">C.</span></span> <span data-ttu-id="817df-143">Verwenden Sie..</span><span class="sxs-lookup"><span data-stu-id="817df-143">Use ..</span></span> <span data-ttu-id="817df-144">Angeben der übergeordneten Achse</span><span class="sxs-lookup"><span data-stu-id="817df-144">to specify the parent axis</span></span>  
 <span data-ttu-id="817df-145">Die folgende Abfrage ruft alle- **\<Order>** Elemente mit einem übergeordneten **\<Customer>** -Element mit dem **CustomerID-** Attribut Wert 1 ab.</span><span class="sxs-lookup"><span data-stu-id="817df-145">The following query retrieves all the **\<Order>** elements with a parent **\<Customer>** element with a **CustomerID** attribute value of 1.</span></span> <span data-ttu-id="817df-146">Die Abfrage verwendet die- `child` Achse im Prädikat, um das übergeordnete Element des-Elements zu finden **\<Order>** .</span><span class="sxs-lookup"><span data-stu-id="817df-146">The query uses the `child` axis in the predicate to find the parent of the **\<Order>** element.</span></span>  
  
```  
/child::Customer/child::Order[../@CustomerID="1"]  
```  
  
 <span data-ttu-id="817df-147">Die `child` Achse ist die Standard Achse.</span><span class="sxs-lookup"><span data-stu-id="817df-147">The `child` axis is the default axis.</span></span> <span data-ttu-id="817df-148">Daher kann die Abfrage wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="817df-148">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer/Order[../@CustomerID="1"]  
```  
  
 <span data-ttu-id="817df-149">Die XPath-Abfrage hat die folgende Entsprechung:</span><span class="sxs-lookup"><span data-stu-id="817df-149">The XPath query is equivalent to:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order.  
```  
  
> [!NOTE]  
>  <span data-ttu-id="817df-150">Die XPath-Abfrage `/Order[../@CustomerID="1"]` gibt einen Fehler zurück, da kein übergeordnetes Element von vorhanden ist **\<Order>** .</span><span class="sxs-lookup"><span data-stu-id="817df-150">The XPath query `/Order[../@CustomerID="1"]` will return an error because there is no parent of **\<Order>**.</span></span> <span data-ttu-id="817df-151">Obwohl möglicherweise Elemente im **\<Order>** Zuordnungsschema vorhanden sind, die enthalten, hat der XPath nicht begonnen **\<Order>** . Folglich wird als Elementtyp der obersten Ebene im Dokument betrachtet.</span><span class="sxs-lookup"><span data-stu-id="817df-151">Although there may be elements in the mapping schema that contain **\<Order>**, the XPath did not begin at any of them; consequently, **\<Order>** is considered to be the top-level element type in the document.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="817df-152">So testen Sie die XPath-Abfrage mit dem Zuordnungsschema</span><span class="sxs-lookup"><span data-stu-id="817df-152">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="817df-153">Kopieren Sie den [Beispiel Schema Code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) , und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="817df-153">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="817df-154">Speichern Sie die Datei unter dem Dateinamen SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="817df-154">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="817df-155">Erstellen Sie die folgende Vorlage (XPathAxesSampleC.xml), und speichern Sie sie im folgenden Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="817df-155">Create the following template (XPathAxesSampleC.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer/Order[../@CustomerID="1"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="817df-156">Der für das Zuordnungsschema (SampleSchema1.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="817df-156">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="817df-157">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="817df-157">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="817df-158">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="817df-158">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="817df-159">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="817df-159">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="817df-160">Im Folgenden finden Sie einen Auszug aus dem Resultset der Vorlagenausführung:</span><span class="sxs-lookup"><span data-stu-id="817df-160">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
         OrderDate="2001-08-01T00:00:00"   
         DueDate="2001-08-13T00:00:00"   
         ShipDate="2001-08-08T00:00:00">  
  <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-761" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-762" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-765" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-768" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-770" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
   ...  
</Order>  
</ROOT>  
```  
  
### <a name="d-specify-the-attribute-axis"></a><span data-ttu-id="817df-161">D:</span><span class="sxs-lookup"><span data-stu-id="817df-161">D.</span></span> <span data-ttu-id="817df-162">Angeben der Attributachse</span><span class="sxs-lookup"><span data-stu-id="817df-162">Specify the attribute axis</span></span>  
 <span data-ttu-id="817df-163">Die folgende XPath-Abfrage wählt alle untergeordneten **\<Customer>** Elemente des Kontext Knotens mit dem **CustomerID-** Attribut Wert 1 aus:</span><span class="sxs-lookup"><span data-stu-id="817df-163">The following XPath query selects all the **\<Customer>** child elements of the context node with a **CustomerID** attribute value of 1:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="1"]  
```  
  
 <span data-ttu-id="817df-164">Im Prädikat `attribute::CustomerID` `attribute` ist die Achse und `CustomerID` ist der Knoten Test (wenn `CustomerID` ein Attribut ist, ist der Knoten Test true, da der **\<attribute>** Knoten der primäre Knoten für die Achse ist `attribute` ).</span><span class="sxs-lookup"><span data-stu-id="817df-164">In the predicate `attribute::CustomerID`, `attribute` is the axis and `CustomerID` is the node test (if `CustomerID` is an attribute the node test is TRUE, because the **\<attribute>** node is the primary node for the `attribute` axis).</span></span>  
  
 <span data-ttu-id="817df-165">Es kann eine Verknüpfung mit der `attribute`-Achse (@) angegeben werden, und da `child` die Standardachse ist, muss sie in der Abfrage nicht angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="817df-165">A shortcut to the `attribute` axis (@) can be specified, and because `child` is the default axis, it can be omitted from the query:</span></span>  
  
```  
/Customer[@CustomerID="1"]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="817df-166">So testen Sie die XPath-Abfrage mit dem Zuordnungsschema</span><span class="sxs-lookup"><span data-stu-id="817df-166">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="817df-167">Kopieren Sie den [Beispiel Schema Code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) , und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="817df-167">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="817df-168">Speichern Sie die Datei unter dem Dateinamen SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="817df-168">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="817df-169">Erstellen Sie die folgende Vorlage (XPathAxesSampleD.xml), und speichern Sie sie in dem Verzeichnis, in dem SampleSchema1.xml gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="817df-169">Create the following template (XPathAxesSampleD.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        child::Customer[attribute::CustomerID="1"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="817df-170">Der für das Zuordnungsschema (SampleSchema1.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="817df-170">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="817df-171">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="817df-171">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="817df-172">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="817df-172">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="817df-173">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="817df-173">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="817df-174">Im Folgenden finden Sie einen Auszug aus dem Resultset der Vorlagenausführung:</span><span class="sxs-lookup"><span data-stu-id="817df-174">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" SalesPersonID="280"   
            TerritoryID="1" AccountNumber="1"   
            CustomerType="S" Orders="Ord-43860 Ord-44501 Ord-45283 Ord-46042">  
    <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
           OrderDate="2001-08-01T00:00:00"   
           DueDate="2001-08-13T00:00:00"   
           ShipDate="2001-08-08T00:00:00">  
       <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
                    OrderQty="1" UnitPriceDiscount="0" />   
       <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
                    OrderQty="1" UnitPriceDiscount="0" />   
       <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
                    OrderQty="1" UnitPriceDiscount="0" />   
      ...   
    </Order>  
   ...  
  </Customer>  
</ROOT>  
```  
  
  
