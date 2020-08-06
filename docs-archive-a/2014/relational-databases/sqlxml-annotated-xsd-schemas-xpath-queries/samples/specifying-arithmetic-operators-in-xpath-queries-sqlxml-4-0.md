---
title: Angeben arithmetischer Operatoren in XPath-Abfragen (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- arithmetic operators
- XPath operators [SQLXML]
- XPath queries [SQLXML], arithmetic operators
- operators [SQLXML]
ms.assetid: fdfbc87d-759f-4abc-acf5-a21de01f78d3
author: rothja
ms.author: jroth
ms.openlocfilehash: 904f3b920029d45d1b72641a19e2ac07befd4def
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608492"
---
# <a name="specifying-arithmetic-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="eae18-102">Angeben von arithmetischen Operatoren in XPath-Abfragen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="eae18-102">Specifying Arithmetic Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="eae18-103">Im folgenden Beispiel wird gezeigt, wie arithmetische Operatoren in XPath-Abfragen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="eae18-103">The following example shows how arithmetic operators are specified in XPath queries.</span></span> <span data-ttu-id="eae18-104">Die XPath-Abfragen in diesem Beispiel werden für das in SampleSchema1.xml enthaltene Zuordnungsschema angegeben.</span><span class="sxs-lookup"><span data-stu-id="eae18-104">The XPath query in this example is specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="eae18-105">Weitere Informationen zu diesem Beispiel Schema finden Sie unter [Beispiel: XSD-Schema mit Anmerkungen für XPath-Beispiele &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="eae18-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="eae18-106">Beispiele</span><span class="sxs-lookup"><span data-stu-id="eae18-106">Examples</span></span>  
  
### <a name="a-specify-the--arithmetic-operator"></a><span data-ttu-id="eae18-107">A.</span><span class="sxs-lookup"><span data-stu-id="eae18-107">A.</span></span> <span data-ttu-id="eae18-108">Angeben des arithmetischen \*-Operators</span><span class="sxs-lookup"><span data-stu-id="eae18-108">Specify the \* arithmetic operator</span></span>  
 <span data-ttu-id="eae18-109">Diese XPath-Abfrage gibt **\<OrderDetail>** Elemente zurück, die das angegebene Prädikat erfüllen:</span><span class="sxs-lookup"><span data-stu-id="eae18-109">This XPath query returns **\<OrderDetail>** elements that satisfy the predicate specified:</span></span>  
  
```  
/child::OrderDetail[@UnitPrice * @Quantity = 12.350]  
```  
  
 <span data-ttu-id="eae18-110">In der Abfrage `child` ist die Achse und `OrderDetail` ist der Knoten Test (true, wenn **Order Detail** ein ist **\<element node>** , da der **\<element>** Knoten der primäre Knoten für die `child` Achse ist).</span><span class="sxs-lookup"><span data-stu-id="eae18-110">In the query, `child` is the axis and `OrderDetail` is the node test (TRUE if **OrderDetail** is an **\<element node>**, because the **\<element>** node is the primary node for the `child` axis).</span></span> <span data-ttu-id="eae18-111">Für alle **\<OrderDetail>** Elementknoten wird der Test im Prädikat angewendet, und es werden nur die Knoten zurückgegeben, die die Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="eae18-111">For all the **\<OrderDetail>** element nodes, the test in the predicate is applied, and only those nodes that satisfy the condition are returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eae18-112">Die in XPath verwendeten Zahlen sind Gleitkommazahlen mit doppelter Genauigkeit, durch Vergleich der Gleitkommazahlen wie im Beispiel werden die Werte gerundet.</span><span class="sxs-lookup"><span data-stu-id="eae18-112">The numbers in XPath are double-precision floating-point numbers, and comparing floating-point numbers as in the example causes rounding.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="eae18-113">So testen Sie die XPath-Abfrage mit dem Zuordnungsschema</span><span class="sxs-lookup"><span data-stu-id="eae18-113">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="eae18-114">Kopieren Sie den [Beispiel Schema Code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) , und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="eae18-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="eae18-115">Speichern Sie die Datei unter dem Dateinamen SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="eae18-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="eae18-116">Erstellen Sie die folgende Vorlage (ArithmeticOperatorA.xml), und speichern Sie sie in dem Verzeichnis, in dem SampleSchema1.xml gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="eae18-116">Create the following template (ArithmeticOperatorA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /OrderDetail[@UnitPrice * @OrderQty = 12.350]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="eae18-117">Der für das Zuordnungsschema (SampleSchema1.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="eae18-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="eae18-118">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="eae18-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="eae18-119">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="eae18-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="eae18-120">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="eae18-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
```  
Here is the partial result set of the template execution:    
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-710" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
   ...  
</ROOT>  
```  
  
  
