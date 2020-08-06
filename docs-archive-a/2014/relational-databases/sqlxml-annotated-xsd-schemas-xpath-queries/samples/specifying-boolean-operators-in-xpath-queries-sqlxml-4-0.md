---
title: Angeben von booleschen Operatoren in XPath-Abfragen (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath operators [SQLXML]
- OR operator
- Boolean operators
- XPath queries [SQLXML], Boolean operators
- operators [SQLXML]
ms.assetid: 9928cff5-62ac-42aa-96bf-2e09a1df0bc3
author: rothja
ms.author: jroth
ms.openlocfilehash: 02dd6e1f120b53382ce984684ea352b36d34b768
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608488"
---
# <a name="specifying-boolean-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="91087-102">Angeben von booleschen Operatoren in XPath-Abfragen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="91087-102">Specifying Boolean Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="91087-103">Im folgenden Beispiel wird dargestellt, wie boolesche Operatoren in XPath-Abfragen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="91087-103">The following example shows how Boolean operators are specified in XPath queries.</span></span> <span data-ttu-id="91087-104">Die XPath-Abfragen in diesem Beispiel werden für das in SampleSchema1.xml enthaltene Zuordnungsschema angegeben.</span><span class="sxs-lookup"><span data-stu-id="91087-104">The XPath query in this example is specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="91087-105">Weitere Informationen zu diesem Beispiel Schema finden Sie unter [Beispiel: XSD-Schema mit Anmerkungen für XPath-Beispiele &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="91087-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="91087-106">Beispiele</span><span class="sxs-lookup"><span data-stu-id="91087-106">Examples</span></span>  
  
### <a name="a-specify-the-or-boolean-operator"></a><span data-ttu-id="91087-107">A.</span><span class="sxs-lookup"><span data-stu-id="91087-107">A.</span></span> <span data-ttu-id="91087-108">Angeben des booleschen OR-Operators</span><span class="sxs-lookup"><span data-stu-id="91087-108">Specify the OR Boolean operator</span></span>  
 <span data-ttu-id="91087-109">Diese XPath-Abfrage gibt die untergeordneten **\<Customer>** -Elemente des Kontext Knotens zurück, deren **CustomerID-** Attribut Wert 13 oder 31 lautet:</span><span class="sxs-lookup"><span data-stu-id="91087-109">This XPath query returns the **\<Customer>** element children of the context node with the **CustomerID** attribute value of 13 or 31:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="13" or attribute::CustomerID="31"]  
```  
  
 <span data-ttu-id="91087-110">Es kann eine Abkürzung für die `attribute`-Achse (@) angegeben werden. Da die `child`-Achse die Standardachse ist, muss sie nicht angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="91087-110">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted:</span></span>  
  
```  
/Customer[@CustomerID="13" or @CustomerID="31"]  
```  
  
 <span data-ttu-id="91087-111">Im Prädikat `attribute` ist die Achse und `CustomerID` ist der Knoten Test (true, wenn **CustomerID** ein Knoten ist **\<attribute>** , da der **\<attribute>** Knoten der primäre Knoten für die Achse ist `attribute` ).</span><span class="sxs-lookup"><span data-stu-id="91087-111">In the predicate, `attribute` is the axis and `CustomerID` is the node test (TRUE if **CustomerID** is an **\<attribute>** node, because the **\<attribute>** node is the primary node for the `attribute` axis).</span></span> <span data-ttu-id="91087-112">Das Prädikat filtert die **\<Customer>** Elemente und gibt nur die Elemente zurück, die die im Prädikat angegebene Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="91087-112">The predicate filters the **\<Customer>** elements and returns only those that satisfy the condition specified in the predicate.</span></span>  
  
##### <a name="to-test-the-xpath-queries-against-the-mapping-schema"></a><span data-ttu-id="91087-113">So testen Sie die XPath-Abfragen mit dem Zuordnungsschema</span><span class="sxs-lookup"><span data-stu-id="91087-113">To test the XPath queries against the mapping schema</span></span>  
  
1.  <span data-ttu-id="91087-114">Kopieren Sie den [Beispiel Schema Code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) , und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="91087-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="91087-115">Speichern Sie die Datei unter dem Dateinamen SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="91087-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="91087-116">Erstellen Sie die folgende Vorlage (BooleanOperatorsA.xml), und speichern Sie sie in dem Verzeichnis, in dem SampleSchema1.xml gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="91087-116">Create the following template (BooleanOperatorsA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="13" or @CustomerID="31"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="91087-117">Der für das Zuordnungsschema (SampleSchema1.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="91087-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="91087-118">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="91087-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="91087-119">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="91087-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="91087-120">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="91087-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="91087-121">Im Folgenden finden Sie das Resultset der Vorlagenausführung:</span><span class="sxs-lookup"><span data-stu-id="91087-121">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="31" SalesPersonID="286" TerritoryID="7" AccountNumber="31" CustomerType="S" Orders="Ord-51803 Ord-69427">  
    <Order SalesOrderID="Ord-51803" SalesPersonID="286" OrderDate="2003-08-01T00:00:00" DueDate="2003-08-13T00:00:00" ShipDate="2003-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-718" UnitPrice="1059.31" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-838" UnitPrice="1059.31" OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
    <Order SalesOrderID="Ord-69427" SalesPersonID="286" OrderDate="2004-05-01T00:00:00" DueDate="2004-05-13T00:00:00" ShipDate="2004-05-08T00:00:00">  
      <OrderDetail ProductID="Prod-835" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
  </Customer>  
</ROOT>  
```  
  
  
