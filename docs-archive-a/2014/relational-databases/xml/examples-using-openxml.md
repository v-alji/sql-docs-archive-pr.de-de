---
title: 'Beispiele: Verwenden von OPENXML | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ColPattern [XML in SQL Server]
- XML [SQL Server], mapping data
- OPENXML statement, about OPENXML statement
- overflow in XML document [SQL Server]
- mapping XML data [SQL Server]
- combining attribute-centric and element centric mapping
- unconsumed data
- attribute-centric mapping
- column patterns [XML in SQL Server]
- XML [SQL Server], overflow handling
- row patterns [XML in SQL Server]
- rowpattern [XML in SQL Server]
- flags parameter
- element-centric mapping [SQL Server]
- edge tables
ms.assetid: 689297f3-adb0-4d8d-bf62-cfda26210164
author: rothja
ms.author: jroth
ms.openlocfilehash: 09fc6ad073b12df2f9fbd8ebc6a59149f6154ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726793"
---
# <a name="examples-using-openxml"></a><span data-ttu-id="417a1-102">Beispiele: Verwenden von OPENXML</span><span class="sxs-lookup"><span data-stu-id="417a1-102">Examples: Using OPENXML</span></span>
  <span data-ttu-id="417a1-103">In den Beispielen dieses Themas wird die Verwendung von OPENXML zum Erstellen einer Rowsetansicht eines XML-Dokuments veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="417a1-103">The examples in this topic show how OPENXML is used to create a rowset view of an XML document.</span></span> <span data-ttu-id="417a1-104">Informationen zur Syntax von OPENXML finden Sie unter [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="417a1-104">For information about the syntax of OPENXML, see [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span></span> <span data-ttu-id="417a1-105">Die Beispiele geben alle Aspekte von OPENXML wieder, ausgenommen der Angabe von Metaeigenschaften in OPENXML.</span><span class="sxs-lookup"><span data-stu-id="417a1-105">The examples show all aspects of OPENXML, but do not specify metaproperties in OPENXML.</span></span> <span data-ttu-id="417a1-106">Weitere Informationen zum Angeben von Metaeigenschaften in OPENXML finden Sie unter [Angeben von Metaeigenschaften in OPENXML](specify-metaproperties-in-openxml.md).</span><span class="sxs-lookup"><span data-stu-id="417a1-106">For more information about how to specify metaproperties in OPENXML, see [Specify Metaproperties in OPENXML](specify-metaproperties-in-openxml.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="417a1-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="417a1-107">Examples</span></span>  
 <span data-ttu-id="417a1-108">Beim Abrufen der Daten wird *rowpattern* zur Identifizierung der Knoten im XML-Dokument, die die Zeilen bestimmen, verwendet.</span><span class="sxs-lookup"><span data-stu-id="417a1-108">In retrieving the data, *rowpattern* is used to identify the nodes in the XML document that determine the rows.</span></span> <span data-ttu-id="417a1-109">*rowpattern* wird in der XPath-Sprache ausgedrückt, die in der MSXML XPath-Implementierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="417a1-109">Additionally, *rowpattern* is expressed in the XPath pattern language that is used in the MSXML XPath implementation.</span></span> <span data-ttu-id="417a1-110">Wenn z. B. das Muster mit einem Element oder Attribut endet, wird eine Zeile für jeden von *rowpattern*ausgewählten Element- oder Attributknoten erstellt.</span><span class="sxs-lookup"><span data-stu-id="417a1-110">For example, if the pattern ends in an element or an attribute, a row is created for each element or attribute node that is selected by *rowpattern*.</span></span>  
  
 <span data-ttu-id="417a1-111">Durch den Wert des *flags* -Parameters wird die Standardzuordnung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="417a1-111">The *flags* value provides default mapping.</span></span> <span data-ttu-id="417a1-112">Wenn kein *ColPattern* in der *SchemaDeclaration*angegeben ist, wird die in *flags* angegebene Zuordnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="417a1-112">If no *ColPattern* is specified in the *SchemaDeclaration*, the mapping specified in *flags* is assumed.</span></span> <span data-ttu-id="417a1-113">Der Wert des *flags* -Parameters wird ignoriert, wenn *ColPattern* in *SchemaDeclaration*angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="417a1-113">The *flags* value is ignored if *ColPattern* is specified in *SchemaDeclaration*.</span></span> <span data-ttu-id="417a1-114">Die Angabe von *ColPattern* bestimmt den Typ der Zuordnung (attributzentriert oder elementzentriert) sowie das Verhalten im Zusammenhang mit Überlaufdaten bzw. nicht verbrauchten Daten.</span><span class="sxs-lookup"><span data-stu-id="417a1-114">The specified *ColPattern* determines the mapping, attribute-centric or element-centric, and also the behavior in dealing with overflow and unconsumed data.</span></span>  
  
### <a name="a-executing-a-simple-select-statement-with-openxml"></a><span data-ttu-id="417a1-115">A.</span><span class="sxs-lookup"><span data-stu-id="417a1-115">A.</span></span> <span data-ttu-id="417a1-116">Ausführen einer einfachen SELECT-Anweisung mit OPENXML</span><span class="sxs-lookup"><span data-stu-id="417a1-116">Executing a simple SELECT statement with OPENXML</span></span>  
 <span data-ttu-id="417a1-117">Das XML-Dokument in diesem Beispiel setzt sich aus den Elementen <`Customer`>, <`Order`> und <`OrderDetail`>zusammen.</span><span class="sxs-lookup"><span data-stu-id="417a1-117">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="417a1-118">Die OPENXML-Anweisung ruft Kundeninformationen in einem zweispaltigen Rowset ( **CustomerID** und **ContactName**) aus dem XML-Dokument ab.</span><span class="sxs-lookup"><span data-stu-id="417a1-118">The OPENXML statement retrieves customer information in a two-column rowset, **CustomerID** and **ContactName**, from the XML document.</span></span>  
  
 <span data-ttu-id="417a1-119">Zunächst wird die gespeicherte Prozedur **sp_xml_preparedocument** aufgerufen, um ein Dokumenthandle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="417a1-119">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="417a1-120">Dieses Dokumenthandle wird an OPENXML weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-120">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="417a1-121">Die OPENXML-Anweisung verdeutlicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="417a1-121">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="417a1-122">*rowpattern* (/ROOT/Customer) identifiziert die zu verarbeitenden <`Customer`>-Knoten.</span><span class="sxs-lookup"><span data-stu-id="417a1-122">*rowpattern* (/ROOT/Customer) identifies the <`Customer`> nodes to process.</span></span>  
  
-   <span data-ttu-id="417a1-123">Der Wert des *flags* -Parameters wird auf **1** festgelegt, was die attributzentrierte Zuordnung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="417a1-123">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="417a1-124">Folglich werden die XML-Attribute den Spalten im Rowset, das in *SchemaDeclaration*definiert ist, zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="417a1-124">As a result, the XML attributes map to the columns in the rowset defined in *SchemaDeclaration*.</span></span>  
  
-   <span data-ttu-id="417a1-125">In *SchemaDeclaration*(in der WITH-Klausel) stimmen die angegebenen Werte für *ColName* mit den entsprechenden XML-Attributnamen überein.</span><span class="sxs-lookup"><span data-stu-id="417a1-125">In *SchemaDeclaration*, in the WITH clause, the specified *ColName* values match the corresponding XML attribute names.</span></span> <span data-ttu-id="417a1-126">Deshalb wird der *ColPattern* -Parameter nicht in *SchemaDeclaration*angegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-126">Therefore, the *ColPattern* parameter is not specified in *SchemaDeclaration*.</span></span>  
  
 <span data-ttu-id="417a1-127">Schließlich ruft die SELECT-Anweisung alle Spalten in dem von OPENXML bereitgestellten Rowset ab.</span><span class="sxs-lookup"><span data-stu-id="417a1-127">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @DocHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
          OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
          OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @DocHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@DocHandle, '/ROOT/Customer',1)  
      WITH (CustomerID  varchar(10),  
            ContactName varchar(20))  
EXEC sp_xml_removedocument @DocHandle  
```  
  
 <span data-ttu-id="417a1-128">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="417a1-128">This is the result:</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="417a1-129">Da die <`Customer`>-Elemente keinerlei Unterelemente besitzen, werden die Werte von **CustomerID** und **ContactName** für beide Kunden als NULL zurückgegeben, wenn dieselbe SELECT-Anweisung mit auf den Wert **2** gesetztem *flags*-Parameter ausgeführt wird, um die elementzentrierte Zuordnung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="417a1-129">Because the <`Customer`> elements do not have any subelements, if the same SELECT statement is executed with *flags* set to **2** to indicate element-centric mapping, the values of **CustomerID** and **ContactName** for both the customers are returned as NULL.</span></span>  
  
 <span data-ttu-id="417a1-130">@xmlDocument kann auch vom Typ **xml** oder **(n)varchar(max)** sein.</span><span class="sxs-lookup"><span data-stu-id="417a1-130">The @xmlDocument can also be of **xml** type or of **(n)varchar(max)** type.</span></span>  
  
 <span data-ttu-id="417a1-131">Wenn <`CustomerID`> und <`ContactName`> im XML-Dokument Unterelemente sind, ruft die elementzentrierte Zuordnung die Werte ab.</span><span class="sxs-lookup"><span data-stu-id="417a1-131">If <`CustomerID`> and <`ContactName`> in the XML document are subelements, the element-centric mapping retrieves the values.</span></span>  
  
```  
DECLARE @XmlDocumentHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer>  
   <CustomerID>VINET</CustomerID>  
   <ContactName>Paul Henriot</ContactName>  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5" OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer>     
   <CustomerID>LILAS</CustomerID>  
   <ContactName>Carlos Gonzlez</ContactName>  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3" OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @XmlDocumentHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT    *  
FROM      OPENXML (@XmlDocumentHandle, '/ROOT/Customer',2)  
           WITH (CustomerID  varchar(10),  
                 ContactName varchar(20))  
EXEC sp_xml_removedocument @XmlDocumentHandle  
```  
  
 <span data-ttu-id="417a1-132">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="417a1-132">This is the result:</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="417a1-133">Beachten Sie, dass das von **sp_xml_preparedocument** zurückgegebene Dokumenthandle für die Dauer des Batches, nicht für die Dauer der Sitzung gültig ist.</span><span class="sxs-lookup"><span data-stu-id="417a1-133">Note that the document handle returned by **sp_xml_preparedocument** is valid for the duration of the batch and not the session.</span></span>  
  
### <a name="b-specifying-colpattern-for-mapping-between-rowset-columns-and-the-xml-attributes-and-elements"></a><span data-ttu-id="417a1-134">B.</span><span class="sxs-lookup"><span data-stu-id="417a1-134">B.</span></span> <span data-ttu-id="417a1-135">Angeben von ColPattern für die Zuordnung zwischen Rowsetspalten und XML-Attributen und -Elementen</span><span class="sxs-lookup"><span data-stu-id="417a1-135">Specifying ColPattern for mapping between rowset columns and the XML attributes and elements</span></span>  
 <span data-ttu-id="417a1-136">In diesem Beispiel wird veranschaulicht, wie das XPath-Muster im optionalen *ColPattern* -Parameter angegeben wird, um für die Zuordnung zwischen Rowsetspalten und XML-Attributen und -Elementen zu sorgen.</span><span class="sxs-lookup"><span data-stu-id="417a1-136">This example shows how the XPath pattern is specified in the optional *ColPattern* parameter to provide mapping between rowset columns and the XML attributes and elements.</span></span>  
  
 <span data-ttu-id="417a1-137">Das XML-Dokument in diesem Beispiel setzt sich aus den Elementen <`Customer`>, <`Order`> und <`OrderDetail`>zusammen.</span><span class="sxs-lookup"><span data-stu-id="417a1-137">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="417a1-138">Die OPENXML-Anweisung ruft Kunden- und Bestellinformationen als Rowset (**CustomerID**, **OrderDate**, **ProdID**und **Qty**) aus dem XML-Dokument ab.</span><span class="sxs-lookup"><span data-stu-id="417a1-138">The OPENXML statement retrieves customer and order information as a rowset (**CustomerID**, **OrderDate**, **ProdID**, and **Qty**) from the XML document.</span></span>  
  
 <span data-ttu-id="417a1-139">Zunächst wird die gespeicherte Prozedur **sp_xml_preparedocument** aufgerufen, um ein Dokumenthandle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="417a1-139">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="417a1-140">Dieses Dokumenthandle wird an OPENXML weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-140">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="417a1-141">Die OPENXML-Anweisung verdeutlicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="417a1-141">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="417a1-142">*rowpattern* (/ROOT/Customer/Order/OrderDetail) identifiziert die zu verarbeitenden <`OrderDetail`>-Knoten.</span><span class="sxs-lookup"><span data-stu-id="417a1-142">*rowpattern* (/ROOT/Customer/Order/OrderDetail) identifies the <`OrderDetail`> nodes to process.</span></span>  
  
 <span data-ttu-id="417a1-143">Zur Veranschaulichung wird der Wert des *flags* -Parameters auf **2** festgelegt, was die attributzentrierte Zuordnung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="417a1-143">For illustration, the *flags* parameter value is set to **2** and indicates element-centric mapping.</span></span> <span data-ttu-id="417a1-144">Allerdings wird diese Zuordnung durch die in *ColPattern* angegebene Zuordnung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="417a1-144">However, the mapping specified in *ColPattern* overwrites this mapping.</span></span> <span data-ttu-id="417a1-145">Das bedeutet, dass das in *ColPattern* angegebene XPath-Muster die Spalten im Rowset Attributen zuordnet.</span><span class="sxs-lookup"><span data-stu-id="417a1-145">That is, the XPath pattern specified in *ColPattern* maps the columns in the rowset to attributes.</span></span> <span data-ttu-id="417a1-146">Dies führt zur attributzentrierten Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="417a1-146">This results in attribute-centric mapping.</span></span>  
  
 <span data-ttu-id="417a1-147">In *SchemaDeclaration*(in der WITH-Klausel) wird *ColPattern* auch mit den Parametern *ColName* und *ColType* angegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-147">In *SchemaDeclaration*, in the WITH clause, *ColPattern* is also specified with the *ColName* and *ColType* parameters.</span></span> <span data-ttu-id="417a1-148">Der optionale *ColPattern* -Parameter entspricht dem angegebenen XPath-Muster und zeigt Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="417a1-148">The optional *ColPattern* is the XPath pattern specified and indicates the following:</span></span>  
  
-   <span data-ttu-id="417a1-149">Die **OrderID**-, **CustomerID**- und **OrderDate**-Spalten im Rowset sind den Attributen des übergeordneten Elements der von *rowpattern* identifizierten Knoten zugeordnet, und *rowpattern* identifiziert die <`OrderDetail`>-Knoten.</span><span class="sxs-lookup"><span data-stu-id="417a1-149">The **OrderID**, **CustomerID**, and **OrderDate** columns in the rowset map to the attributes of the parent of the nodes identified by *rowpattern*, and *rowpattern* identifies the <`OrderDetail`> nodes.</span></span> <span data-ttu-id="417a1-150">Deshalb sind die **CustomerID**- und **OrderDate**-Spalten den **CustomerID**- und **OrderDate**-Attributen des <`Order`>-Elements zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="417a1-150">Therefore, the **CustomerID** and **OrderDate** columns map to **CustomerID** and **OrderDate** attributes of the <`Order`> element.</span></span>  
  
-   <span data-ttu-id="417a1-151">Die **ProdID** - und **Qty** -Spalten im Rowset sind den Attributen **ProductID** und **Quantity** der in *rowpattern*identifizierten Knoten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="417a1-151">The **ProdID** and **Qty** columns in the rowset map to the **ProductID** and **Quantity** attributes of the nodes identified in *rowpattern*.</span></span>  
  
 <span data-ttu-id="417a1-152">Schließlich ruft die SELECT-Anweisung alle Spalten in dem von OPENXML bereitgestellten Rowset ab.</span><span class="sxs-lookup"><span data-stu-id="417a1-152">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @XmlDocumentHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
           OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
           OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @XmlDocumentHandle OUTPUT, @XmlDocument  
-- Execute a SELECT stmt using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@XmlDocumentHandle, '/ROOT/Customer/Order/OrderDetail',2)  
WITH (OrderID     int         '../@OrderID',  
      CustomerID  varchar(10) '../@CustomerID',  
      OrderDate   datetime    '../@OrderDate',  
      ProdID      int         '@ProductID',  
      Qty         int         '@Quantity')  
EXEC sp_xml_removedocument @XmlDocumentHandle  
```  
  
 <span data-ttu-id="417a1-153">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="417a1-153">This is the result:</span></span>  
  
```  
OrderID CustomerID        OrderDate          ProdID    Qty  
-------------------------------------------------------------  
10248    VINET     1996-07-04 00:00:00.000     11       12  
10248    VINET     1996-07-04 00:00:00.000     42       10  
10283    LILAS     1996-08-16 00:00:00.000     72        3  
```  
  
 <span data-ttu-id="417a1-154">Das als *ColPattern* angegebene XPath-Muster kann auch angegeben werden, um die XML-Elemente den Rowsetspalten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="417a1-154">The XPath pattern specified as *ColPattern* can also be specified to map the XML elements to the rowset columns.</span></span> <span data-ttu-id="417a1-155">Dies führt zur elementzentrierten Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="417a1-155">This results in element-centric mapping.</span></span> <span data-ttu-id="417a1-156">Im folgenden Beispiel sind die XML-Dokumentelemente <`CustomerID`> und <`OrderDate`> Unterelemente des <`Orders`>-Elements.</span><span class="sxs-lookup"><span data-stu-id="417a1-156">In the following example, the XML document <`CustomerID`> and <`OrderDate`> are subelements of the <`Orders`> element.</span></span> <span data-ttu-id="417a1-157">Da *ColPattern* die im *flags* -Parameter angegebene Zuordnung überschreibt, wird der *flags* -Parameter nicht in OPENXML angegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-157">Because *ColPattern* overwrites the mapping specified in the *flags* parameter, the *flags* parameter is not specified in OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order EmployeeID="5" >  
      <OrderID>10248</OrderID>  
      <CustomerID>VINET</CustomerID>  
      <OrderDate>1996-07-04T00:00:00</OrderDate>  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order  EmployeeID="3" >  
      <OrderID>10283</OrderID>  
      <CustomerID>LILAS</CustomerID>  
      <OrderDate>1996-08-16T00:00:00</OrderDate>  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer/Order/OrderDetail')  
WITH (CustomerID  varchar(10)   '../CustomerID',  
      OrderDate   datetime      '../OrderDate',  
      ProdID      int           '@ProductID',  
      Qty         int           '@Quantity')  
EXEC sp_xml_removedocument @docHandle  
```  
  
### <a name="c-combining-attribute-centric-and-element-centric-mapping"></a><span data-ttu-id="417a1-158">C.</span><span class="sxs-lookup"><span data-stu-id="417a1-158">C.</span></span> <span data-ttu-id="417a1-159">Kombinieren der attributzentrierten und der elementzentrierten Zuordnung</span><span class="sxs-lookup"><span data-stu-id="417a1-159">Combining attribute-centric and element-centric mapping</span></span>  
 <span data-ttu-id="417a1-160">In diesem Beispiel ist der *flags* -Parameter auf den Wert **3** festgelegt und zeigt an, dass sowohl die attributzentrierte als auch die elementzentrierte Zuordnung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="417a1-160">In this example, the *flags* parameter is set to **3** and indicates that both attribute-centric and element-centric mapping will be applied.</span></span> <span data-ttu-id="417a1-161">In diesem Fall wird zuerst die attributzentrierte Zuordnung und anschließend die elementzentrierte Zuordnung auf alle noch nicht verarbeiteten Spalten angewendet.</span><span class="sxs-lookup"><span data-stu-id="417a1-161">In this case, the attribute-centric mapping is applied first, and then element-centric mapping is applied for all the columns not yet dealt with.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument =N'<ROOT>  
<Customer CustomerID="VINET"  >  
     <ContactName>Paul Henriot</ContactName>  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
          OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" >   
     <ContactName>Carlos Gonzlez</ContactName>  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
          OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @XmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer',3)  
      WITH (CustomerID  varchar(10),  
            ContactName varchar(20))  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="417a1-162">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="417a1-162">This is the result</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="417a1-163">Für **CustomerID**wird die attributzentrierte Zuordnung angewendet.</span><span class="sxs-lookup"><span data-stu-id="417a1-163">The attribute-centric mapping is applied for **CustomerID**.</span></span> <span data-ttu-id="417a1-164">Es gibt kein **ContactName**-Attribut im <`Customer`>-Element.</span><span class="sxs-lookup"><span data-stu-id="417a1-164">There is no **ContactName** attribute in the <`Customer`> element.</span></span> <span data-ttu-id="417a1-165">Deshalb wird die elementzentrierte Zuordnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="417a1-165">Therefore, element-centric mapping is applied.</span></span>  
  
### <a name="d-specifying-the-text-xpath-function-as-colpattern"></a><span data-ttu-id="417a1-166">D:</span><span class="sxs-lookup"><span data-stu-id="417a1-166">D.</span></span> <span data-ttu-id="417a1-167">Angeben der text() XPath-Funktion als ColPattern</span><span class="sxs-lookup"><span data-stu-id="417a1-167">Specifying the text() XPath function as ColPattern</span></span>  
 <span data-ttu-id="417a1-168">Das XML-Dokument in diesem Beispiel setzt sich aus den Elementen <`Customer`> und <`Order`> zusammen.</span><span class="sxs-lookup"><span data-stu-id="417a1-168">The XML document in this example is made up of the <`Customer`> and <`Order`> elements.</span></span> <span data-ttu-id="417a1-169">Die OPENXML-Anweisung ruft ein Rowset ab, das sich aus dem **oid**-Attribut aus dem <`Order`>-Element, aus der ID des übergeordneten Elements des durch *rowpattern* identifizierten Knotens und aus der Blattwertzeichenfolge des Elementinhalts zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="417a1-169">The OPENXML statement retrieves a rowset that is made up of the **oid** attribute from the <`Order`> element, the ID of the parent of the node identified by *rowpattern*, and the leaf-value string of the element content.</span></span>  
  
 <span data-ttu-id="417a1-170">Zunächst wird die gespeicherte Prozedur **sp_xml_preparedocument** aufgerufen, um ein Dokumenthandle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="417a1-170">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="417a1-171">Dieses Dokumenthandle wird an OPENXML weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-171">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="417a1-172">Die OPENXML-Anweisung verdeutlicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="417a1-172">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="417a1-173">*rowpattern* (/root/Customer/Order) identifiziert die zu verarbeitenden <`Order`>-Knoten.</span><span class="sxs-lookup"><span data-stu-id="417a1-173">*rowpattern* (/root/Customer/Order) identifies the <`Order`> nodes to process.</span></span>  
  
-   <span data-ttu-id="417a1-174">Der Wert des *flags* -Parameters wird auf **1** festgelegt, was die attributzentrierte Zuordnung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="417a1-174">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="417a1-175">Folglich werden die XML-Attribute den in *SchemaDeclaration*definierten Rowsetspalten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="417a1-175">As a result, the XML attributes map to the rowset columns defined in *SchemaDeclaration*.</span></span>  
  
-   <span data-ttu-id="417a1-176">In *SchemaDeclaration* (in der WITH-Klausel) stimmen die Rowsetspaltennamen **oid** und **amount** mit den entsprechenden XML-Attributnamen überein.</span><span class="sxs-lookup"><span data-stu-id="417a1-176">In *SchemaDeclaration* in the WITH clause, the **oid** and **amount** rowset column names match the corresponding XML attribute names.</span></span> <span data-ttu-id="417a1-177">Deshalb wird der *ColPattern* -Parameter nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-177">Therefore, the *ColPattern* parameter is not specified.</span></span> <span data-ttu-id="417a1-178">Für die **comment** -Spalte im Rowset wird die XPath-Funktion **text()** als *ColPattern*angegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-178">For the **comment** column in the rowset, the XPath function, **text()**, is specified as *ColPattern*.</span></span> <span data-ttu-id="417a1-179">Dadurch wird die im *flags*-Parameter angegebene attributzentrierte Zuordnung überschrieben, und die Spalte enthält die Blattwert-Zeichenfolge des Elementinhalts.</span><span class="sxs-lookup"><span data-stu-id="417a1-179">This overwrites the attribute-centric mapping specified in *flags*, and the column contains the leaf-value string of the element content.</span></span>  
  
 <span data-ttu-id="417a1-180">Schließlich ruft die SELECT-Anweisung alle Spalten in dem von OPENXML bereitgestellten Rowset ab.</span><span class="sxs-lookup"><span data-stu-id="417a1-180">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
--sample XML document  
SET @xmlDocument =N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied  
      </Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
            <Urgency>Important</Urgency>  
            Happy Customer.  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/root/Customer/Order', 1)  
     WITH (oid     char(5),   
           amount  float,   
           comment ntext 'text()')  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="417a1-181">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="417a1-181">This is the result:</span></span>  
  
```  
oid   amount        comment  
----- -----------   -----------------------------  
O1    3.5           NULL  
O2    13.4          Customer was very satisfied  
O3    100.0         Happy Customer.  
O4    10000.0       NULL  
```  
  
### <a name="e-specifying-tablename-in-the-with-clause"></a><span data-ttu-id="417a1-182">E.</span><span class="sxs-lookup"><span data-stu-id="417a1-182">E.</span></span> <span data-ttu-id="417a1-183">Angeben von TableName in der WITH-Klausel</span><span class="sxs-lookup"><span data-stu-id="417a1-183">Specifying TableName in the WITH clause</span></span>  
 <span data-ttu-id="417a1-184">In diesem Beispiel ist *TableName* in der WITH-Klausel anstelle von *SchemaDeclaration*angegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-184">This example specifies *TableName* in the WITH clause instead of *SchemaDeclaration*.</span></span> <span data-ttu-id="417a1-185">Dies erweist sich bei einer Tabelle, die die von Ihnen gewünschte Struktur aufweist und bei der keine Spaltenmuster ( *ColPattern* -Parameter) notwendig sind, als hilfreich.</span><span class="sxs-lookup"><span data-stu-id="417a1-185">This is useful if you have a table that has the structure you want and no column patterns, *ColPattern* parameter, are required.</span></span>  
  
 <span data-ttu-id="417a1-186">Das XML-Dokument in diesem Beispiel setzt sich aus den Elementen <`Customer`> und <`Order`> zusammen.</span><span class="sxs-lookup"><span data-stu-id="417a1-186">The XML document in this example is made up of the <`Customer`> and <`Order`> elements.</span></span> <span data-ttu-id="417a1-187">Die OPENXML-Anweisung ruft Bestellinformationen in einem dreispaltigen Rowset (**oid**, **date**und **amount**) aus dem XML-Dokument ab.</span><span class="sxs-lookup"><span data-stu-id="417a1-187">The OPENXML statement retrieves order information in a three-column rowset (**oid**, **date**, and **amount**) from the XML document.</span></span>  
  
 <span data-ttu-id="417a1-188">Zunächst wird die gespeicherte Prozedur **sp_xml_preparedocument** aufgerufen, um ein Dokumenthandle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="417a1-188">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="417a1-189">Dieses Dokumenthandle wird an OPENXML weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-189">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="417a1-190">Die OPENXML-Anweisung verdeutlicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="417a1-190">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="417a1-191">*rowpattern* (/root/Customer/Order) identifiziert die zu verarbeitenden <`Order`>-Knoten.</span><span class="sxs-lookup"><span data-stu-id="417a1-191">*rowpattern* (/root/Customer/Order) identifies the <`Order`> nodes to process.</span></span>  
  
-   <span data-ttu-id="417a1-192">Die WITH-Klausel enthält *SchemaDeclaration* nicht.</span><span class="sxs-lookup"><span data-stu-id="417a1-192">There is no *SchemaDeclaration* in the WITH clause.</span></span> <span data-ttu-id="417a1-193">Anstelle dessen wird ein Tabellenname angegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-193">Instead, a table name is specified.</span></span> <span data-ttu-id="417a1-194">Deshalb wird das Tabellenschema als Rowsetschema verwendet.</span><span class="sxs-lookup"><span data-stu-id="417a1-194">Therefore, the table schema is used as the rowset schema.</span></span>  
  
-   <span data-ttu-id="417a1-195">Der Wert des *flags* -Parameters wird auf **1** festgelegt, was die attributzentrierte Zuordnung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="417a1-195">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="417a1-196">Somit werden Attribute der Elemente (identifiziert durch *rowpattern*) den Rowsetspalten mit gleichen Namen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="417a1-196">Therefore, attributes of the elements, identified by *rowpattern*, map to the rowset columns with the same name.</span></span>  
  
 <span data-ttu-id="417a1-197">Schließlich ruft die SELECT-Anweisung alle Spalten in dem von OPENXML bereitgestellten Rowset ab.</span><span class="sxs-lookup"><span data-stu-id="417a1-197">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
-- Create a test table. This table schema is used by OPENXML as the  
-- rowset schema.  
CREATE TABLE T1(oid char(5), date datetime, amount float)  
GO  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
-- Sample XML document  
SET @xmlDocument =N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very   
             satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
--Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/root/Customer/Order', 1)  
     WITH T1  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="417a1-198">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="417a1-198">This is the result:</span></span>  
  
```  
oid   date                        amount  
----- --------------------------- ----------  
O1    1996-01-20 00:00:00.000     3.5  
O2    1997-04-30 00:00:00.000     13.4  
O3    1999-07-14 00:00:00.000     100.0  
O4    1996-01-20 00:00:00.000     10000.0  
```  
  
### <a name="f-obtaining-the-result-in-an-edge-table-format"></a><span data-ttu-id="417a1-199">F.</span><span class="sxs-lookup"><span data-stu-id="417a1-199">F.</span></span> <span data-ttu-id="417a1-200">Ausgeben von Ergebnissen im Rahmentabellenformat</span><span class="sxs-lookup"><span data-stu-id="417a1-200">Obtaining the result in an edge table format</span></span>  
 <span data-ttu-id="417a1-201">In diesem Beispiel wird die WITH-Klausel nicht in der OPENXML-Anweisung angegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-201">In this example, the WITH clause is not specified in the OPENXML statement.</span></span> <span data-ttu-id="417a1-202">Folglich weist das von OPENXML generierte Rowset ein Rahmentabellenformat auf.</span><span class="sxs-lookup"><span data-stu-id="417a1-202">As a result, the rowset generated by OPENXML has an edge table format.</span></span> <span data-ttu-id="417a1-203">Die SELECT-Anweisung gibt alle Spalten in der Rahmentabelle zurück.</span><span class="sxs-lookup"><span data-stu-id="417a1-203">The SELECT statement returns all the columns in the edge table.</span></span>  
  
 <span data-ttu-id="417a1-204">Das Beispiel-XML-Dokument im Beispiel setzt sich aus den Elementen <`Customer`>, <`Order`> und <`OrderDetail`>zusammen.</span><span class="sxs-lookup"><span data-stu-id="417a1-204">The sample XML document in the example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span>  
  
 <span data-ttu-id="417a1-205">Zunächst wird die gespeicherte Prozedur **sp_xml_preparedocument** aufgerufen, um ein Dokumenthandle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="417a1-205">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="417a1-206">Dieses Dokumenthandle wird an OPENXML weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-206">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="417a1-207">Die OPENXML-Anweisung verdeutlicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="417a1-207">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="417a1-208">*rowpattern* (/ROOT/Customer) identifiziert die zu verarbeitenden <`Customer`>-Knoten.</span><span class="sxs-lookup"><span data-stu-id="417a1-208">*rowpattern* (/ROOT/Customer) identifies the <`Customer`> nodes to process.</span></span>  
  
-   <span data-ttu-id="417a1-209">Die WITH-Klausel wird nicht bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="417a1-209">The WITH clause is not provided.</span></span> <span data-ttu-id="417a1-210">Deshalb gibt OPENXML das Rowset in einem Rahmentabellenformat zurück.</span><span class="sxs-lookup"><span data-stu-id="417a1-210">Therefore, OPENXML returns the rowset in an edge table format.</span></span>  
  
 <span data-ttu-id="417a1-211">Schließlich gibt die SELECT-Anweisung alle Spalten in der Rahmentabelle zurück.</span><span class="sxs-lookup"><span data-stu-id="417a1-211">The SELECT statement then retrieves all the columns in the edge table.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
SET @xmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order CustomerID="VINET" EmployeeID="5" OrderDate=  
           "1996-07-04T00:00:00">  
      <OrderDetail OrderID="10248" ProductID="11" Quantity="12"/>  
      <OrderDetail OrderID="10248" ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order CustomerID="LILAS" EmployeeID="3" OrderDate=  
           "1996-08-16T00:00:00">  
      <OrderDetail OrderID="10283" ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
--Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer')  
  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="417a1-212">Das Ergebnis wird in Form einer Rahmentabelle zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-212">The result is returned as an edge table.</span></span> <span data-ttu-id="417a1-213">Informationen erhalten Sie durch Abfragen, die Sie für die Rahmentabelle schreiben.</span><span class="sxs-lookup"><span data-stu-id="417a1-213">You can write queries against the edge table to obtain information.</span></span> <span data-ttu-id="417a1-214">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="417a1-214">For example:</span></span>  
  
-   <span data-ttu-id="417a1-215">Die folgende Abfrage gibt die Anzahl der **Customer** -Knoten im Dokument zurück.</span><span class="sxs-lookup"><span data-stu-id="417a1-215">The following query returns the number of **Customer** nodes in the document.</span></span> <span data-ttu-id="417a1-216">Da die WITH-Klausel nicht angegeben ist, gibt OPENXML eine Rahmentabelle zurück.</span><span class="sxs-lookup"><span data-stu-id="417a1-216">Because the WITH clause is not specified, OPENXML returns an edge table.</span></span> <span data-ttu-id="417a1-217">Die SELECT-Anweisung fragt die Rahmentabelle ab.</span><span class="sxs-lookup"><span data-stu-id="417a1-217">The SELECT statement queries the edge table.</span></span>  
  
    ```  
    SELECT count(*)  
    FROM OPENXML(@docHandle, '/')  
    WHERE localname = 'Customer'  
    ```  
  
-   <span data-ttu-id="417a1-218">Die folgende Abfrage gibt die lokalen Namen der XML-Knoten vom Typ element zurück.</span><span class="sxs-lookup"><span data-stu-id="417a1-218">The following query returns the local names of XML nodes of element type.</span></span>  
  
    ```  
    SELECT distinct localname   
    FROM OPENXML(@docHandle, '/')   
    WHERE nodetype = 1   
    ORDER BY localname  
    ```  
  
### <a name="g-specifying-rowpattern-ending-with-an-attribute"></a><span data-ttu-id="417a1-219">G.</span><span class="sxs-lookup"><span data-stu-id="417a1-219">G.</span></span> <span data-ttu-id="417a1-220">Angeben von "rowpattern", das mit einem Attribut endet</span><span class="sxs-lookup"><span data-stu-id="417a1-220">Specifying rowpattern ending with an attribute</span></span>  
 <span data-ttu-id="417a1-221">Das XML-Dokument in diesem Beispiel setzt sich aus den Elementen <`Customer`>, <`Order`> und <`OrderDetail`>zusammen.</span><span class="sxs-lookup"><span data-stu-id="417a1-221">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="417a1-222">Die OPENXML-Anweisung ruft Bestelldetailinformationen in einem dreispaltigen Rowset (**ProductID**, **Quantity**und **OrderID**) aus dem XML-Dokument ab.</span><span class="sxs-lookup"><span data-stu-id="417a1-222">The OPENXML statement retrieves information about the order details in a three-column rowset (**ProductID**, **Quantity**, and **OrderID**) from the XML document.</span></span>  
  
 <span data-ttu-id="417a1-223">Zunächst wird **sp_xml_preparedocument** aufgerufen, um ein Dokumenthandle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="417a1-223">First, the **sp_xml_preparedocument** is called to obtain a document handle.</span></span> <span data-ttu-id="417a1-224">Dieses Dokumenthandle wird an OPENXML weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-224">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="417a1-225">Die OPENXML-Anweisung verdeutlicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="417a1-225">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="417a1-226">*rowpattern* (/ROOT/Customer/Order/OrderDetail/\@ProductID) endet mit einem XML-Attribut, **ProductID**.</span><span class="sxs-lookup"><span data-stu-id="417a1-226">*rowpattern* (/ROOT/Customer/Order/OrderDetail/\@ProductID) ends with an XML attribute, **ProductID**.</span></span> <span data-ttu-id="417a1-227">Im resultierenden Rowset wird für jeden im XML-Dokument ausgewählten Attributknoten eine Zeile erstellt.</span><span class="sxs-lookup"><span data-stu-id="417a1-227">In the resulting rowset, a row is created for each attribute node selected in the XML document.</span></span>  
  
-   <span data-ttu-id="417a1-228">In diesem Beispiel wird der *flags* -Parameter nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-228">In this example, the *flags* parameter is not specified.</span></span> <span data-ttu-id="417a1-229">Vielmehr werden die Zuordnungen vom *ColPattern* -Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-229">Instead, the mappings are specified by the *ColPattern* parameter.</span></span>  
  
 <span data-ttu-id="417a1-230">In *SchemaDeclaration* (in der WITH-Klausel) wird *ColPattern* auch mit den Parametern *ColName* und *ColType* angegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-230">In *SchemaDeclaration* in the WITH clause, *ColPattern* is also specified with the *ColName* and *ColType* parameters.</span></span> <span data-ttu-id="417a1-231">Der optionale *ColPattern* -Parameter entspricht dem angegebenen XPath-Muster und zeigt Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="417a1-231">The optional *ColPattern* is the XPath pattern specified to indicate the following:</span></span>  
  
-   <span data-ttu-id="417a1-232">Das als**ColPattern**für die *ProdID* -Spalte im Rowset angegebene XPath-Muster ( **.** ) identifiziert den Kontextknoten (aktueller Knoten).</span><span class="sxs-lookup"><span data-stu-id="417a1-232">The XPath pattern (**.**) specified as *ColPattern* for the **ProdID** column in the rowset identifies the context node, current node.</span></span> <span data-ttu-id="417a1-233">Laut Angabe in *rowpattern* ist das das **ProductID**-Attribut des <`OrderDetail`>-Elements.</span><span class="sxs-lookup"><span data-stu-id="417a1-233">As per the *rowpattern* specified, it is the **ProductID** attribute of the <`OrderDetail`> element.</span></span>  
  
-   <span data-ttu-id="417a1-234">Das für die **Qty**-Spalte im Rowset angegebene *ColPattern* **(../\@Quantity**) identifiziert das **Quantity**-Attribut des übergeordneten Knotens (<`OrderDetail`>) des Kontextknotens (\<ProductID>).</span><span class="sxs-lookup"><span data-stu-id="417a1-234">The *ColPattern*, **../\@Quantity**, specified for the **Qty** column in the rowset identifies the **Quantity** attribute of the parent, <`OrderDetail`>, node of the context node, \<ProductID>.</span></span>  
  
-   <span data-ttu-id="417a1-235">In gleicher Weise identifiziert das für die **OID**-Spalte im Rowset angegebene *ColPattern* ( **../../\@OrderID**) das **OrderID**-Attribut des übergeordneten Knotens (<`Order`>) des Kontextknotens.</span><span class="sxs-lookup"><span data-stu-id="417a1-235">Similarly, the *ColPattern*, **../../\@OrderID**, specified for the **OID** column in the rowset identifies the **OrderID** attribute of the parent, <`Order`>, of the parent node of the context node.</span></span> <span data-ttu-id="417a1-236">Der übergeordnete Knoten ist <`OrderDetail`>, und der Kontextknoten <`ProductID`>.</span><span class="sxs-lookup"><span data-stu-id="417a1-236">The parent node is <`OrderDetail`>, and the context node is <`ProductID`>.</span></span>  
  
 <span data-ttu-id="417a1-237">Schließlich ruft die SELECT-Anweisung alle Spalten in dem von OPENXML bereitgestellten Rowset ab.</span><span class="sxs-lookup"><span data-stu-id="417a1-237">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
--Sample XML document  
SET @xmlDocument =N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5" OrderDate=  
           "1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3" OrderDate=  
           "1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer/Order/OrderDetail/@ProductID')  
       WITH ( ProdID  int '.',  
              Qty     int '../@Quantity',  
              OID     int '../../@OrderID')  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="417a1-238">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="417a1-238">This is the result:</span></span>  
  
```  
ProdID      Qty         OID  
----------- ----------- -------   
11          12          10248  
42          10          10248  
72          3           10283  
```  
  
### <a name="h-specifying-an-xml-document-that-has-multiple-text-nodes"></a><span data-ttu-id="417a1-239">H.</span><span class="sxs-lookup"><span data-stu-id="417a1-239">H.</span></span> <span data-ttu-id="417a1-240">Angeben eines XML-Dokuments mit mehreren Textknoten</span><span class="sxs-lookup"><span data-stu-id="417a1-240">Specifying an XML document that has multiple text nodes</span></span>  
 <span data-ttu-id="417a1-241">Sind mehrere Textknoten in einem XML-Dokument vorhanden, gibt eine SELECT-Anweisung mit *ColPattern*( **text()** ) nur den ersten anstelle aller Textknoten zurück.</span><span class="sxs-lookup"><span data-stu-id="417a1-241">If you have multiple text nodes in an XML document, a SELECT statement with a *ColPattern*, **text()**, returns only the first text node, instead of all of them.</span></span> <span data-ttu-id="417a1-242">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="417a1-242">For example:</span></span>  
  
```  
DECLARE @h int  
EXEC sp_xml_preparedocument @h OUTPUT,  
         N'<root xmlns:a="urn:1">  
           <a:Elem abar="asdf">  
             T<a>a</a>U  
           </a:Elem>  
         </root>',  
         '<ns xmlns:b="urn:1" />'  
  
SELECT * FROM openxml(@h, '/root/b:Elem')  
      WITH (Col1 varchar(20) 'text()')  
EXEC sp_xml_removedocument @h  
```  
  
 <span data-ttu-id="417a1-243">Die SELECT-Anweisung gibt **T** als Ergebnis zurück (und nicht **TaU**).</span><span class="sxs-lookup"><span data-stu-id="417a1-243">The SELECT statement returns **T** as the result, and not **TaU**.</span></span>  
  
### <a name="i-specifying-the-xml-data-type-in-the-with-clause"></a><span data-ttu-id="417a1-244">I.</span><span class="sxs-lookup"><span data-stu-id="417a1-244">I.</span></span> <span data-ttu-id="417a1-245">Angeben des XML-Datentyps in der WITH-Klausel</span><span class="sxs-lookup"><span data-stu-id="417a1-245">Specifying the xml data type in the WITH clause</span></span>  
 <span data-ttu-id="417a1-246">In der WITH-Klausel muss ein Spaltenmuster, das der **xml** -Datentypspalte (typisiert oder nicht typisiert) zugeordnet ist, entweder eine leere Sequenz oder eine Sequenz aus Elementen, Produktionsanweisungen, Textknoten und Kommentaren zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-246">In the WITH clause, a column pattern that is mapped to the **xml** data type column, whether typed or untyped, must return either an empty sequence or a sequence of elements, processing instructions, text nodes, and comments.</span></span> <span data-ttu-id="417a1-247">Die Daten werden in einen **xml** -Datentyp umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="417a1-247">The data is cast to an **xml** data type.</span></span>  
  
 <span data-ttu-id="417a1-248">Im folgenden Beispiel schließt die Tabellenschemadeklaration in der WITH-Klausel **xml** -Typspalten ein.</span><span class="sxs-lookup"><span data-stu-id="417a1-248">In the following example, the table schema declaration in the WITH clause includes **xml** type columns.</span></span>  
  
```  
DECLARE @h int  
DECLARE @x xml  
set @x = '<Root>  
  <row id="1"><lname>Duffy</lname>  
   <Address>  
            <Street>111 Maple</Street>  
            <City>Seattle</City>  
   </Address>  
  </row>  
  <row id="2"><lname>Wang</lname>  
   <Address>  
            <Street>222 Pine</Street>  
            <City>Bothell</City>  
   </Address>  
  </row>  
</Root>'  
  
EXEC sp_xml_preparedocument @h output, @x  
SELECT *  
FROM   OPENXML (@h, '/Root/row', 10)  
      WITH (id int '@id',  
  
            lname    varchar(30),  
            xmlname  xml 'lname',  
            OverFlow xml '@mp:xmltext')  
EXEC sp_xml_removedocument @h  
```  
  
 <span data-ttu-id="417a1-249">Konkret wird eine **xml** -Typvariable (\@x) an die **sp_xml_preparedocument()** -Funktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-249">Specifically, you are passing an **xml** type variable (\@x) to the **sp_xml_preparedocument()** function.</span></span>  
  
 <span data-ttu-id="417a1-250">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="417a1-250">This is the result:</span></span>  
  
```  
id  lname   xmlname                   OverFlow  
--- ------- ------------------------------ -------------------------------  
1   Duffy   <lname>Duffy</lname>  <row><Address>  
                                   <Street>111 Maple</Street>  
                                   <City>Seattle</City>  
                                  </Address></row>  
2   Wang    <lname>Wang</lname>   <row><Address>  
                                    <Street>222 Pine</Street>  
                                    <City>Bothell</City>  
                                   </Address></row>  
```  
  
 <span data-ttu-id="417a1-251">Beachten Sie Folgendes im Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="417a1-251">Note the following from the result:</span></span>  
  
-   <span data-ttu-id="417a1-252">Für die **lname**-Spalte des **varchar(30)** -Typs wird der Wert aus dem entsprechenden <`lname`>-Element abgerufen.</span><span class="sxs-lookup"><span data-stu-id="417a1-252">For the **lname** column of **varchar(30)** type, its value is retrieved from the corresponding <`lname`> element.</span></span>  
  
-   <span data-ttu-id="417a1-253">Für die **xmlname** -Spalte des **xml** -Typs wird dasselbe Namenselement als Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-253">For the **xmlname** column of **xml** type, the same name element is returned as its value.</span></span>  
  
-   <span data-ttu-id="417a1-254">Das Flag wird auf 10 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="417a1-254">The flag is set to 10.</span></span> <span data-ttu-id="417a1-255">Der Wert 10 bedeutet "2 + 8", wobei 2 die elementzentrierte Zuordnung anzeigt und 8 anzeigt, dass nur nicht verbrauchte XML-Daten zur OverFlow-Spalte hinzugefügt werden sollen, die in der WITH-Klausel definiert ist.</span><span class="sxs-lookup"><span data-stu-id="417a1-255">The 10 means 2 + 8, where 2 indicates element-centric mapping and 8 indicates that only unconsumed XML data should be added to the OverFlow column defined in the WITH clause.</span></span> <span data-ttu-id="417a1-256">Wenn Sie den flags-Parameter auf den Wert 2 festlegen, wird das gesamte XML-Dokument in die OverFlow-Spalte kopiert, die in der WITH-Klausel angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="417a1-256">If you set the flag to 2, the whole XML document is copied to the OverFlow column that is specified in the WITH clause.</span></span>  
  
-   <span data-ttu-id="417a1-257">Falls es sich bei der Spalte in der WITH-Klausel um eine typisierte XML-Spalte handelt und die XML-Instanz nicht zum Schema passt, wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="417a1-257">In case the column in the WITH clause is a typed XML column and the XML instance does not confirm to the schema, an error is returned.</span></span>  
  
### <a name="j-retrieving-individual-values-from-multivalued-attributes"></a><span data-ttu-id="417a1-258">J.</span><span class="sxs-lookup"><span data-stu-id="417a1-258">J.</span></span> <span data-ttu-id="417a1-259">Abrufen einzelner Werte aus mehrwertigen Attributen</span><span class="sxs-lookup"><span data-stu-id="417a1-259">Retrieving individual values from multivalued attributes</span></span>  
 <span data-ttu-id="417a1-260">Ein XML-Dokument kann mehrwertige Attribute enthalten.</span><span class="sxs-lookup"><span data-stu-id="417a1-260">An XML document can have attributes that are multivalued.</span></span> <span data-ttu-id="417a1-261">Das **IDREFS** -Attribut kann beispielsweise mehrwertig sein.</span><span class="sxs-lookup"><span data-stu-id="417a1-261">For example, the **IDREFS** attribute can be multivalued.</span></span> <span data-ttu-id="417a1-262">Die Werte von mehrwertigen Attributen werden in einem XML-Dokument als Zeichenfolge angegeben, wobei die Werte durch ein Leerzeichen voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="417a1-262">In an XML document, the multivalued attribute values are specified as a string, with the values separated by a space.</span></span> <span data-ttu-id="417a1-263">Im folgenden XML-Dokument sind das **attends**-Attribut des \<Student>-Elements und das **attendedBy**-Attribut des \<Class>-Elements mehrwertige Attribute.</span><span class="sxs-lookup"><span data-stu-id="417a1-263">In the following XML document, the **attends** attribute of the \<Student> element and the **attendedBy** attribute of \<Class> are multivalued.</span></span> <span data-ttu-id="417a1-264">Für das Abrufen einzelner Werte aus einem mehrwertigen XML-Attribut und das Speichern jedes einzelnen Wertes in einer separaten Zeile in der Datenbank ist zusätzliche Arbeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="417a1-264">Retrieving individual values from a multivalued XML attribute and storing each value in a separate row in the database requires additional work.</span></span> <span data-ttu-id="417a1-265">Dieser Vorgang wird in dem folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="417a1-265">This example shows the process.</span></span>  
  
 <span data-ttu-id="417a1-266">Dieses XML-Beispieldokument besteht aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="417a1-266">This sample XML document is made up of the following elements:</span></span>  
  
-   \<Student>  
  
     <span data-ttu-id="417a1-267">Die Attribute **id** (Studenten-ID), **name**und **attends** .</span><span class="sxs-lookup"><span data-stu-id="417a1-267">The **id** (student ID), **name**, and **attends** attributes.</span></span> <span data-ttu-id="417a1-268">Das **attends** -Attribut ist ein mehrwertiges Attribut.</span><span class="sxs-lookup"><span data-stu-id="417a1-268">The **attends** attribute is a multivalued attribute.</span></span>  
  
-   \<Class>  
  
     <span data-ttu-id="417a1-269">Die Attribute **id** (Klassen-ID), **name**und **attendedBy** .</span><span class="sxs-lookup"><span data-stu-id="417a1-269">The **id** (class ID), **name**, and **attendedBy** attributes.</span></span> <span data-ttu-id="417a1-270">Das **attendedBy** -Attribut ist ein mehrwertiges Attribut.</span><span class="sxs-lookup"><span data-stu-id="417a1-270">The **attendedBy** attribute is a multivalued attribute.</span></span>  
  
 <span data-ttu-id="417a1-271">Das **attends**-Attribut in \<Student> und das **attendedBy**-Attribut in \<Class> stellen eine **m:n**-Beziehung zwischen den Tabellen „Student“ und „Class“ dar.</span><span class="sxs-lookup"><span data-stu-id="417a1-271">The **attends** attribute in \<Student> and the **attendedBy** attribute in \<Class> represent a **m:n** relationship between the Student and Class tables.</span></span> <span data-ttu-id="417a1-272">Ein Student kann viele Kurse besuchen, und ein Kurs kann über viele Studenten verfügen.</span><span class="sxs-lookup"><span data-stu-id="417a1-272">A student can take many classes and a class can have many students.</span></span>  
  
 <span data-ttu-id="417a1-273">Angenommen, Sie möchten dieses Dokument aufteilen und in der Datenbank wie folgt speichern:</span><span class="sxs-lookup"><span data-stu-id="417a1-273">Assume that you want to shred this document and save it in the database as shown in the following:</span></span>  
  
-   <span data-ttu-id="417a1-274">Speichern Sie die \<Student>-Daten in der Students-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="417a1-274">Save the \<Student> data in the Students table.</span></span>  
  
-   <span data-ttu-id="417a1-275">Speichern Sie die \<Class>-Daten in der Courses-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="417a1-275">Save the \<Class> data in the Courses table.</span></span>  
  
-   <span data-ttu-id="417a1-276">Speichern der **m:n** -Beziehung der Daten (zwischen Student und Class) in der CourseAttendence-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="417a1-276">Save the **m:n** relationship data, between Student and Class, in the CourseAttendence table.</span></span> <span data-ttu-id="417a1-277">Zum Extrahieren der Werte ist zusätzliche Arbeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="417a1-277">Additional work is required to extract the values.</span></span> <span data-ttu-id="417a1-278">Verwenden Sie zum Abrufen dieser Informationen und Speichern in der Tabelle die folgenden gespeicherten Prozeduren:</span><span class="sxs-lookup"><span data-stu-id="417a1-278">To retrieve this information and store it in the table, use these stored procedures:</span></span>  
  
    -   <span data-ttu-id="417a1-279">**Insert_Idrefs_Values**</span><span class="sxs-lookup"><span data-stu-id="417a1-279">**Insert_Idrefs_Values**</span></span>  
  
         <span data-ttu-id="417a1-280">Fügt die Werte für die Kurs-ID und Studenten-ID in die CourseAttendence-Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="417a1-280">Inserts the values of course ID and student ID in the CourseAttendence table.</span></span>  
  
    -   <span data-ttu-id="417a1-281">**Extract_idrefs_values**</span><span class="sxs-lookup"><span data-stu-id="417a1-281">**Extract_idrefs_values**</span></span>  
  
         <span data-ttu-id="417a1-282">Extrahiert die einzelnen Studenten-IDs aus jedem \<Course>-Element.</span><span class="sxs-lookup"><span data-stu-id="417a1-282">Extracts the individual student IDs from each \<Course> element.</span></span> <span data-ttu-id="417a1-283">Zum Abrufen dieser Werte wird eine Rahmentabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="417a1-283">An edge table is used to retrieve these values.</span></span>  
  
 <span data-ttu-id="417a1-284">Im Folgenden werden die Schritte aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="417a1-284">Here are the steps:</span></span>  
  
```  
-- Create these tables:  
DROP TABLE CourseAttendance  
DROP TABLE Students  
DROP TABLE Courses  
GO  
CREATE TABLE Students(  
                id   varchar(5) primary key,  
                name varchar(30)  
                )  
GO  
CREATE TABLE Courses(  
               id       varchar(5) primary key,  
               name     varchar(30),  
               taughtBy varchar(5)  
)  
GO  
CREATE TABLE CourseAttendance(  
             id         varchar(5) references Courses(id),  
             attendedBy varchar(5) references Students(id),  
             constraint CourseAttendance_PK primary key (id, attendedBy)  
)  
go  
-- Create these stored procedures:  
DROP PROCEDURE f_idrefs  
GO  
CREATE PROCEDURE f_idrefs  
    @t      varchar(500),  
    @idtab  varchar(50),  
    @id     varchar(5)  
AS  
DECLARE @sp int  
DECLARE @att varchar(5)  
SET @sp = 0  
WHILE (LEN(@t) > 0)  
BEGIN   
    SET @sp = CHARINDEX(' ', @t+ ' ')  
    SET @att = LEFT(@t, @sp-1)  
    EXEC('INSERT INTO '+@idtab+' VALUES ('''+@id+''', '''+@att+''')')  
    SET @t = SUBSTRING(@t+ ' ', @sp+1, LEN(@t)+1-@sp)  
END  
Go  
  
DROP PROCEDURE fill_idrefs  
GO  
CREATE PROCEDURE fill_idrefs   
    @xmldoc     int,  
    @xpath      varchar(100),  
    @from       varchar(50),  
    @to         varchar(50),  
    @idtable    varchar(100)  
AS  
DECLARE @t varchar(500)  
DECLARE @id varchar(5)  
  
/* Temporary edge table */  
SELECT *   
INTO #TempEdge   
FROM OPENXML(@xmldoc, @xpath)  
  
DECLARE fillidrefs_cursor CURSOR FOR  
    SELECT CAST(iv.text AS nvarchar(200)) AS id,  
           CAST(av.text AS nvarchar(4000)) AS refs  
    FROM   #TempEdge c, #TempEdge i,  
           #TempEdge iv, #TempEdge a, #TempEdge av  
    WHERE  c.id = i.parentid  
    AND    UPPER(i.localname) = UPPER(@from)  
    AND    i.id = iv.parentid  
    AND    c.id = a.parentid  
    AND    UPPER(a.localname) = UPPER(@to)  
    AND    a.id = av.parentid  
  
OPEN fillidrefs_cursor  
FETCH NEXT FROM fillidrefs_cursor INTO @id, @t  
WHILE (@@FETCH_STATUS <> -1)  
BEGIN  
    IF (@@FETCH_STATUS <> -2)  
    BEGIN  
        execute f_idrefs @t, @idtable, @id  
    END  
    FETCH NEXT FROM fillidrefs_cursor INTO @id, @t  
END  
CLOSE fillidrefs_cursor  
DEALLOCATE fillidrefs_cursor  
Go  
-- This is the sample document that is shredded and the data is stored in the preceding tables.  
DECLARE @h int  
EXECUTE sp_xml_preparedocument @h OUTPUT, N'<Data>  
  <Student id = "s1" name = "Student1"  attends = "c1 c3 c6"  />  
  <Student id = "s2" name = "Student2"  attends = "c2 c4" />  
  <Student id = "s3" name = "Student3"  attends = "c2 c4 c6" />  
  <Student id = "s4" name = "Student4"  attends = "c1 c3 c5" />  
  <Student id = "s5" name = "Student5"  attends = "c1 c3 c5 c6" />  
  <Student id = "s6" name = "Student6" />  
  
  <Class id = "c1" name = "Intro to Programming"   
         attendedBy = "s1 s4 s5" />  
  <Class id = "c2" name = "Databases"   
         attendedBy = "s2 s3" />  
  <Class id = "c3" name = "Operating Systems"   
         attendedBy = "s1 s4 s5" />  
  <Class id = "c4" name = "Networks" attendedBy = "s2 s3" />  
  <Class id = "c5" name = "Algorithms and Graphs"   
         attendedBy =  "s4 s5"/>  
  <Class id = "c6" name = "Power and Pragmatism"   
         attendedBy = "s1 s3 s5" />  
</Data>'  
  
INSERT INTO Students SELECT * FROM OPENXML(@h, '//Student') WITH Students  
  
INSERT INTO Courses SELECT * FROM OPENXML(@h, '//Class') WITH Courses  
/* Using the edge table */  
EXECUTE fill_idrefs @h, '//Class', 'id', 'attendedby', 'CourseAttendance'  
  
SELECT * FROM Students  
SELECT * FROM Courses  
SELECT * FROM CourseAttendance  
  
EXECUTE sp_xml_removedocument @h  
```  
  
### <a name="k-retrieving-binary-from-base64-encoded-data-in-xml"></a><span data-ttu-id="417a1-285">K.</span><span class="sxs-lookup"><span data-stu-id="417a1-285">K.</span></span> <span data-ttu-id="417a1-286">Abrufen von Binärdaten aus Base64-codierten Daten in XML</span><span class="sxs-lookup"><span data-stu-id="417a1-286">Retrieving binary from base64 encoded data in XML</span></span>  
 <span data-ttu-id="417a1-287">Binärdaten sind häufig mithilfe der Base64-Codierung in das XML-Dokument eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="417a1-287">Binary data is frequently included in XML using base64 encoding.</span></span> <span data-ttu-id="417a1-288">Wenn Sie dieses XML-Dokument durch Verwenden von OPENXML aufteilen, erhalten Sie die Base64-codierten Daten.</span><span class="sxs-lookup"><span data-stu-id="417a1-288">When you shred this XML by using OPENXML, you receive the base64 encoded data.</span></span> <span data-ttu-id="417a1-289">Dieses Beispiel zeigt, wie Sie die Base64-codierten Daten zurück in Binärdaten konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="417a1-289">This example shows how you can convert the base64 encoded data back to binary.</span></span>  
  
-   <span data-ttu-id="417a1-290">Erstellen Sie eine Tabelle mit Beispielbinärdaten.</span><span class="sxs-lookup"><span data-stu-id="417a1-290">Create a table with sample binary data.</span></span>  
  
-   <span data-ttu-id="417a1-291">Verwenden Sie eine FOR XML-Abfrage und die Option BINARY BASE64, um ein XML-Dokument zu konstruieren, in denen die Binärdaten Base64-codiert sind.</span><span class="sxs-lookup"><span data-stu-id="417a1-291">Use a FOR XML query and the BINARY BASE64 option to construct XML that has the binary data encoded as base64.</span></span>  
  
-   <span data-ttu-id="417a1-292">Teilen Sie das XML-Dokument mithilfe von OPENXML auf.</span><span class="sxs-lookup"><span data-stu-id="417a1-292">Shred the XML by using OPENXML.</span></span> <span data-ttu-id="417a1-293">Die von OPENXML zurückgegebenen Daten sind Base64-codierte Daten.</span><span class="sxs-lookup"><span data-stu-id="417a1-293">The data returned by OPENXML will be base64 encoded data.</span></span> <span data-ttu-id="417a1-294">Rufen Sie als Nächstes die .value-Funktion auf, um sie wieder zurück in Binärdateien zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="417a1-294">Next, call the .value function to convert it back to binary.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 varbinary(100))  
go  
-- Insert sample binary data  
INSERT T VALUES(1, 0x1234567890)   
go  
 -- Create test XML document that has base64 encoded binary data (use FOR XML query and specify BINARY BASE64 option)  
SELECT * FROM T  
FOR XML AUTO, BINARY BASE64  
go  
-- result  
-- <T Col1="1" Col2="EjRWeJA="/>  
  
-- Now shredd the sample XML using OPENXML.   
-- Call the .value function to convert   
-- the base64 encoded data returned by OPENXML to binary.  
DECLARE @h int ;  
EXEC sp_xml_preparedocument @h OUTPUT, '<T Col1="1" Col2="EjRWeJA="/>' ;  
SELECT Col1,   
CAST('<binary>' + Col2 + '</binary>' AS XML).value('.', 'varbinary(max)') AS BinaryCol   
FROM openxml(@h, '/T')   
WITH (Col1 integer, Col2 varchar(max)) ;  
EXEC sp_xml_removedocument @h ;  
GO  
```  
  
 Dies ist das Ergebnis. <span data-ttu-id="417a1-296">Die zurückgegebenen Binärdaten sind die ursprünglichen Binärdaten in Tabelle T.</span><span class="sxs-lookup"><span data-stu-id="417a1-296">The binary data returned is the original binary data in table T.</span></span>  
  
```  
Col1        BinaryCol  
----------- ---------------------  
1           0x1234567890  
```  
  
## <a name="see-also"></a><span data-ttu-id="417a1-297">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="417a1-297">See Also</span></span>  
 <span data-ttu-id="417a1-298">[sp_xml_preparedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="417a1-298">[sp_xml_preparedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql) </span></span>  
 <span data-ttu-id="417a1-299">[sp_xml_removedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="417a1-299">[sp_xml_removedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql) </span></span>  
 <span data-ttu-id="417a1-300">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="417a1-300">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="417a1-301">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="417a1-301">OPENXML &#40;SQL Server&#41;</span></span>](openxml-sql-server.md)  
  
  
