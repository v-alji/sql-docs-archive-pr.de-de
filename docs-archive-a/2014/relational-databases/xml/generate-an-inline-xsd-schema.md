---
title: Generieren eines XSD-Inlineschemas | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XSD schemas [SQL Server]
- XMLSCHEMA option
- schemas [SQL Server], XML
- XDR schemas
- FOR XML clause, inline XSD schema generation
- inline XSD schema generation [SQL Server]
- XMLDATA option
ms.assetid: 04b35145-1cca-45f4-9eb7-990abf2e647d
author: rothja
ms.author: jroth
ms.openlocfilehash: 2af748d4fc6ae67f57568be58ec7f59876098f52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726753"
---
# <a name="generate-an-inline-xsd-schema"></a><span data-ttu-id="89ae5-102">Generieren eines XSD-Inlineschemas</span><span class="sxs-lookup"><span data-stu-id="89ae5-102">Generate an Inline XSD Schema</span></span>
  <span data-ttu-id="89ae5-103">In einer FOR XML-Klausel können Sie anfordern, dass die Abfrage ein Inlineschema zusammen mit den Abfrageergebnissen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="89ae5-103">In a FOR XML clause, you can request that your query return an inline schema together with the query results.</span></span> <span data-ttu-id="89ae5-104">Wenn Sie ein XDR-Schema wünschen, verwenden Sie das XMLDATA-Schlüsselwort in der FOR XML-Klausel.</span><span class="sxs-lookup"><span data-stu-id="89ae5-104">If you want an XDR schema, you use the XMLDATA keyword in the FOR XML clause.</span></span> <span data-ttu-id="89ae5-105">Wenn Sie ein XSD-Schema wünschen, verwenden Sie das XMLSCHEMA-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="89ae5-105">If you want an XSD schema, you use the XMLSCHEMA keyword.</span></span>  
  
 <span data-ttu-id="89ae5-106">Dieses Thema beschreibt das XMLSCHEMA-Schlüsselwort und erläutert die Struktur des sich ergebenden XSD-Inlineschemas.</span><span class="sxs-lookup"><span data-stu-id="89ae5-106">This topic describes the XMLSCHEMA keyword and explains the structure of the resulting inline XSD schema.</span></span> <span data-ttu-id="89ae5-107">Die folgenden Einschränkungen gelten beim Anfordern von Inlineschemas:</span><span class="sxs-lookup"><span data-stu-id="89ae5-107">Following are the limitations when you are requesting inline schemas:</span></span>  
  
-   <span data-ttu-id="89ae5-108">Sie können XMLSCHEMA nur im RAW- und AUTO-Modus angeben, nicht im EXPLICIT-Modus.</span><span class="sxs-lookup"><span data-stu-id="89ae5-108">You can specify XMLSCHEMA only in RAW and AUTO mode, not in EXPLICIT mode.</span></span>  
  
-   <span data-ttu-id="89ae5-109">Wenn eine geschachtelte FOR XML-Abfrage die TYPE-Direktive angibt, ist das Abfrageergebnis vom Typ `xml`, und dieses Ergebnis wird als eine Instanz nicht typisierter XML-Daten behandelt.</span><span class="sxs-lookup"><span data-stu-id="89ae5-109">If a nested FOR XML query specifies the TYPE directive, the query result is of `xml` type, and this result is treated as an instance of untyped XML data.</span></span> <span data-ttu-id="89ae5-110">Weitere Informationen finden Sie unter [XML-Daten &#40;SQL Server&#41;](xml-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="89ae5-110">For more information, see [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="89ae5-111">Wenn Sie XMLSCHEMA in einer FOR XML-Abfrage angeben, erhalten Sie sowohl ein Schema als auch XML-Daten als Abfrageergebnis.</span><span class="sxs-lookup"><span data-stu-id="89ae5-111">When you specify XMLSCHEMA in a FOR XML query, you receive both a schema and XML data, the query result.</span></span> <span data-ttu-id="89ae5-112">Jedes Datenelement der obersten Ebene verweist mithilfe einer Standard-Namespacedeklaration auf das vorherige Schema, das seinerseits auf den Zielnamespace des Inlineschemas verweist.</span><span class="sxs-lookup"><span data-stu-id="89ae5-112">Each top-level element of the data refers to the previous schema by using a default namespace declaration that, in turn, refers to the target namespace of the inline schema.</span></span>  
  
 <span data-ttu-id="89ae5-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="89ae5-113">For example:</span></span>  
  
```  
<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="Production.ProductModel">  
    <xsd:complexType>  
      <xsd:attribute name="ProductModelID" type="sqltypes:int" use="required" />  
      <xsd:attribute name="Name" use="required">  
        <xsd:simpleType sqltypes:sqlTypeAlias="[AdventureWorks2012].[dbo].[Name]">  
          <xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033" sqltypes:sqlCompareOptions="IgnoreCase IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">  
            <xsd:maxLength value="50" />  
          </xsd:restriction>  
        </xsd:simpleType>  
      </xsd:attribute>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
<Production.ProductModel xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" ProductModelID="1" Name="Classic Vest" />  
```  
  
 <span data-ttu-id="89ae5-114">Das Ergebnis enthält das XML-Schema und das XML-Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="89ae5-114">The result includes XML schema and the XML result.</span></span> <span data-ttu-id="89ae5-115">Das <`ProductModel`>-Element der obersten Ebene im Ergebnis verweist mithilfe der Standard-Namespacedeklaration xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" auf das Schema.</span><span class="sxs-lookup"><span data-stu-id="89ae5-115">The <`ProductModel`> top-level element in the result refers to the schema by using the default namespace declaration, xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" .</span></span>  
  
 <span data-ttu-id="89ae5-116">Der Schemateil des Ergebnisses kann mehrere Schemadokumente enthalten, die mehrere Namespaces beschreiben.</span><span class="sxs-lookup"><span data-stu-id="89ae5-116">The schema part of the result may contain multiple schema documents that describe multiple namespaces.</span></span> <span data-ttu-id="89ae5-117">Es werden mindestens die beiden folgenden Schemadokumente zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="89ae5-117">At a minimum, the following two schema documents are returned:</span></span>  
  
-   <span data-ttu-id="89ae5-118">Ein Schemadokument für den **Sqltypes** -Namespace, für das die SQL-Basistypen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="89ae5-118">One schema document for the **Sqltypes** namespace, and for which the base SQL types are being returned.</span></span>  
  
-   <span data-ttu-id="89ae5-119">Ein weiteres Schemadokument, das die Form des FOR XML-Abfrageergebnisses beschreibt.</span><span class="sxs-lookup"><span data-stu-id="89ae5-119">Another schema document that describes the shape of the FOR XML query result.</span></span>  
  
 <span data-ttu-id="89ae5-120">Wenn typisierte `xml`-Datentypen im Abfrageergebnis enthalten sind, werden die Schemas, die diesen typisierten `xml`-Datentypen zugeordnet sind, ebenfalls eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="89ae5-120">Also, if any typed `xml` data types are included in the query result, the schemas associated with those typed `xml` data types are included.</span></span>  
  
 <span data-ttu-id="89ae5-121">Der Zielnamespace des Schemadokuments, das die Form des FOR XML-Ergebnisses beschreibt, enthält einen festen Teil und einen numerischen Teil, der automatisch inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="89ae5-121">The target namespace of the schema document that describes the shape of the FOR XML result contains a fixed portion and a numeric portion that increments automatically.</span></span> <span data-ttu-id="89ae5-122">Das Format dieses Namespace wird im folgenden Beispiel gezeigt; dabei ist *n* eine positive ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="89ae5-122">The format of this namespace is shown in the following where *n* is a positive integer.</span></span> <span data-ttu-id="89ae5-123">In der vorherigen Abfrage ist z. B. urn:schemas-microsoft-com:sql:SqlRowSet1 der Zielnamespace.</span><span class="sxs-lookup"><span data-stu-id="89ae5-123">For example, in the previous query, urn:schemas-microsoft-com:sql:SqlRowSet1 is the target namespace.</span></span>  
  
```  
urn:schemas-microsoft-com:sql:SqlRowSetn  
```  
  
 <span data-ttu-id="89ae5-124">Die Änderung in den Zielnamespaces, die zwischen den einzelnen Ausführungen auftritt, kann unerwünscht sein.</span><span class="sxs-lookup"><span data-stu-id="89ae5-124">The change in the target namespaces in the result that occurred from one execution to another may not be desirable.</span></span> <span data-ttu-id="89ae5-125">Wenn Sie z. B. das sich ergebende XML abfragen, wird durch die Änderung im Zielnamespace ein Update der Abfrage erforderlich.</span><span class="sxs-lookup"><span data-stu-id="89ae5-125">For example, if you query the resulting XML, the change in target namespace will require that you update your query.</span></span> <span data-ttu-id="89ae5-126">Sie können optional einen Zielnamespace angeben, wenn die Option XMLSCHEMA in der FOR XML-Klausel hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="89ae5-126">You can optionally specify a target namespace when the XMLSCHEMA option is added in the FOR XML clause.</span></span> <span data-ttu-id="89ae5-127">Das sich ergebende XML enthält den von Ihnen bereitgestellten Namespace und bleibt unabhängig davon gleich, wie häufig die Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="89ae5-127">The resulting XML will include the namespace you provided and will remain the same, regardless of how many times you run the query.</span></span>  
  
```  
SELECT ProductModelID, Name  
FROM   Production.ProductModel  
WHERE ProductModelID=1  
FOR XML AUTO, XMLSCHEMA ('MyURI')  
```  
  
## <a name="entity-elements"></a><span data-ttu-id="89ae5-128">Entitätselemente</span><span class="sxs-lookup"><span data-stu-id="89ae5-128">Entity Elements</span></span>  
 <span data-ttu-id="89ae5-129">Um die Einzelheiten der XSD-Schemastruktur behandeln zu können, die für das Abfrageergebnis generiert wird, muss zuerst das Entitätselement beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="89ae5-129">In order to discuss the details of the XSD schema structure generated for the query result, the entity element has to first be described</span></span>  
  
 <span data-ttu-id="89ae5-130">Ein Entitätselement in den XML-Daten, die durch eine FOR XML-Abfrage zurückgegeben werden, ist ein Element, das aus einer Tabelle und nicht aus einer Spalte generiert wird.</span><span class="sxs-lookup"><span data-stu-id="89ae5-130">An entity element in the XML data returned by FOR XML query is an element that is generated from a table and not from a column.</span></span> <span data-ttu-id="89ae5-131">Die folgende FOR XML-Abfrage gibt z. B. Kontaktinformationen aus der `Person` -Tabelle in der `AdventureWorks2012` -Datenbank zurück.</span><span class="sxs-lookup"><span data-stu-id="89ae5-131">For example, the following FOR XML query returns contact information from the `Person` table in the `AdventureWorks2012` database.</span></span>  
  
```  
SELECT BusinessEntityID, FirstName  
FROM Person.Person  
WHERE BusinessEntityID = 1  
FOR XML AUTO, ELEMENTS  
```  
  
 <span data-ttu-id="89ae5-132">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="89ae5-132">This is the result:</span></span>  
  
 `<Person>`  
  
 `<BusinessEntityID>1</BusinessEntityID>`  
  
 `<FirstName>Ken</FirstName>`  
  
 `</Person>`  
  
 <span data-ttu-id="89ae5-133">In diesem Ergebnis ist <`Person`> das Entitätselement.</span><span class="sxs-lookup"><span data-stu-id="89ae5-133">In this result, <`Person`> is the entity element.</span></span> <span data-ttu-id="89ae5-134">Das XML-Ergebnis kann mehrere Entitätselemente enthalten, von denen jedes eine globale Deklaration im XSD-Inlineschema besitzt.</span><span class="sxs-lookup"><span data-stu-id="89ae5-134">There can be multiple entity elements in the XML result and each of these has a global declaration in the inline XSD schema.</span></span> <span data-ttu-id="89ae5-135">Die folgende Abfrage ruft z. B. Bestellungskopfzeilen- und Detailinformationen für eine bestimmte Bestellung ab.</span><span class="sxs-lookup"><span data-stu-id="89ae5-135">For example, the following query retrieves sales order header and detail information for a specific order.</span></span>  
  
```  
SELECT  SalesOrderHeader.SalesOrderID, ProductID, OrderQty  
FROM    Sales.SalesOrderHeader, Sales.SalesOrderDetail  
WHERE   SalesOrderHeader.SalesOrderID = SalesOrderDetail.SalesOrderID  
AND     SalesOrderHeader.SalesOrderID=5001  
FOR XML AUTO, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="89ae5-136">Da die Abfrage die ELEMENTS-Direktive angibt, ist das sich ergebende XML elementzentriert.</span><span class="sxs-lookup"><span data-stu-id="89ae5-136">Because the query specifies the ELEMENTS directive, the resulting XML is element-centric.</span></span> <span data-ttu-id="89ae5-137">Die Abfrage gibt außerdem die XMLSCHEMA-Direktive an.</span><span class="sxs-lookup"><span data-stu-id="89ae5-137">The query also specifies the XMLSCHEMA directive.</span></span> <span data-ttu-id="89ae5-138">Daher wird ein XSD-Inlineschema zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="89ae5-138">Therefore, an inline XSD schema is returned.</span></span> <span data-ttu-id="89ae5-139">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="89ae5-139">This is the result:</span></span>  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />`  
  
 `<xsd:element name="Sales.SalesOrderHeader">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="SalesOrderID" type="sqltypes:int" />`  
  
 `<xsd:element ref="schema:Sales.SalesOrderDetail" minOccurs="0" maxOccurs="unbounded" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `<xsd:element name="Sales.SalesOrderDetail">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" />`  
  
 `<xsd:element name="OrderQty" type="sqltypes:smallint" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 <span data-ttu-id="89ae5-140">Beachten Sie hinsichtlich der vorherigen Abfrage Folgendes:</span><span class="sxs-lookup"><span data-stu-id="89ae5-140">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="89ae5-141">Im Ergebnis sind <`SalesOrderHeader`> und <`SalesOrderDetail`> Entitätselemente.</span><span class="sxs-lookup"><span data-stu-id="89ae5-141">In the result, <`SalesOrderHeader`> and <`SalesOrderDetail`> are entity elements.</span></span> <span data-ttu-id="89ae5-142">Aus diesem Grund werden sie global im Schema deklariert.</span><span class="sxs-lookup"><span data-stu-id="89ae5-142">Because of this, they are globally declared in the schema.</span></span> <span data-ttu-id="89ae5-143">Dies bedeutet, dass die Deklaration auf der obersten Ebene im <`Schema`>-Element erfolgt.</span><span class="sxs-lookup"><span data-stu-id="89ae5-143">That is, the declaration appears at the top level inside the <`Schema`> element.</span></span>  
  
-   <span data-ttu-id="89ae5-144"><`SalesOrderID`>, <`ProductID`> und <`OrderQty`> sind keine Entitätselemente, da sie Spalten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="89ae5-144">The <`SalesOrderID`>, <`ProductID`>, and <`OrderQty`> are not entity elements, because they map to columns.</span></span> <span data-ttu-id="89ae5-145">Die Spaltendaten werden aufgrund der ELEMENTS-Direktive als Elemente im XML zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="89ae5-145">The column data is returned as elements in the XML, because of the ELEMENTS directive.</span></span> <span data-ttu-id="89ae5-146">Diese werden lokalen Elementen des complex-Typs des Entitätselements zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="89ae5-146">These are mapped to local elements of the entity element's complex type.</span></span> <span data-ttu-id="89ae5-147">Beachten Sie, dass die `SalesOrderID`-, `ProductID` - und `OrderQty` -Werte lokalen Attributen des entsprechenden complex-Typs des Entitätselements zugeordnet werden, wenn die ELEMENTS-Direktive nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="89ae5-147">Note that if the ELEMENTS directive is not specified, the `SalesOrderID`, `ProductID` and `OrderQty` values are mapped to local attributes of the corresponding entity element's complex type.</span></span>  
  
## <a name="attribute-name-clashes"></a><span data-ttu-id="89ae5-148">Attributnamenkollisionen</span><span class="sxs-lookup"><span data-stu-id="89ae5-148">Attribute Name Clashes</span></span>  
 <span data-ttu-id="89ae5-149">Die folgende Diskussion basiert auf den Tabellen `CustOrder` und `CustOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="89ae5-149">The following discussion is based on the `CustOrder` and `CustOrderDetail` tables.</span></span> <span data-ttu-id="89ae5-150">Wenn Sie die folgenden Beispiele testen möchten, erstellen Sie diese Tabellen und fügen eigene Beispieldaten hinzu:</span><span class="sxs-lookup"><span data-stu-id="89ae5-150">To test the following samples, create these tables and add your own sample data:</span></span>  
  
```  
CREATE TABLE CustOrder (OrderID int primary key, CustomerID int)  
GO  
CREATE TABLE CustOrderDetail (OrderID int, ProductID int, Qty int)  
GO  
```  
  
 <span data-ttu-id="89ae5-151">In FOR XML wird der gleiche Name manchmal zum Angeben verschiedener Eigenschaften oder Attribute verwendet.</span><span class="sxs-lookup"><span data-stu-id="89ae5-151">In FOR XML, the same name is sometimes used to indicate different properties, attributes.</span></span> <span data-ttu-id="89ae5-152">Die folgende attributzentrierte Abfrage im RAW-Modus generiert z. B. zwei Attribute, die den gleichen Namen (OrderID) besitzen.</span><span class="sxs-lookup"><span data-stu-id="89ae5-152">For example, the following attribute-centric RAW mode query generates two attributes that have the same name, OrderID.</span></span> <span data-ttu-id="89ae5-153">In diesem Fall wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="89ae5-153">This generates an error.</span></span>  
  
```  
SELECT CustOrder.OrderID,   
       CustOrderDetail.ProductID,   
       CustOrderDetail.OrderID  
FROM   dbo.CustOrder, dbo.CustOrderDetail  
WHERE  CustOrder.OrderID = CustOrderDetail.OrderID  
FOR XML RAW, XMLSCHEMA  
```  
  
 <span data-ttu-id="89ae5-154">Da es jedoch zulässig ist, zwei Elemente mit gleichem Namen zu verwenden, können Sie das Problem durch Hinzufügen der ELEMENTS-Direktive beseitigen:</span><span class="sxs-lookup"><span data-stu-id="89ae5-154">However, because it is acceptable to have two elements that have the same name, you can eliminate the problem by adding the ELEMENTS directive:</span></span>  
  
```  
SELECT CustOrder.OrderID,  
       CustOrderDetail.ProductID,   
       CustOrderDetail.OrderID  
from   dbo.CustOrder, dbo.CustOrderDetail  
where  CustOrder.OrderID = CustOrderDetail.OrderID  
FOR XML RAW, XMLSCHEMA, ELEMENTS  
```  
  
 <span data-ttu-id="89ae5-155">Dies ist das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="89ae5-155">This is the result.</span></span> <span data-ttu-id="89ae5-156">Beachten Sie, dass das OrderID-Element im XSD-Inlineschema zweimal definiert wird.</span><span class="sxs-lookup"><span data-stu-id="89ae5-156">Note in the inline XSD schema, the OrderID element is defined two times.</span></span> <span data-ttu-id="89ae5-157">In einer der Deklarationen wird minOccurs entsprechend der OrderID aus der CustOrderDetail-Tabelle auf 0 festgelegt, in der zweiten Deklaration erfolgt die Zuordnung zur primären Schlüsselspalte OrderID der `CustOrder` -Tabelle, wobei minOccurs standardmäßig den Wert 1 besitzt.</span><span class="sxs-lookup"><span data-stu-id="89ae5-157">One of the declarations has minOccurs set to 0, corresponding to the OrderID from the CustOrderDetail table, and the second one maps to the OrderID primary key column of the `CustOrder` table where minOccurs is 1 by default.</span></span>  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="OrderID" type="sqltypes:int" />`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" minOccurs="0" />`  
  
 `<xsd:element name="OrderID" type="sqltypes:int" minOccurs="0" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
## <a name="element-name-clashes"></a><span data-ttu-id="89ae5-158">Elementnamenkollisionen</span><span class="sxs-lookup"><span data-stu-id="89ae5-158">Element Name Clashes</span></span>  
 <span data-ttu-id="89ae5-159">In FOR XML kann der gleiche Name zum Angeben von zwei Unterelementen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89ae5-159">In FOR XML, the same name can be used to indicate two subelements.</span></span> <span data-ttu-id="89ae5-160">Die folgende Abfrage ruft z. B. die ListPrice- und DealerPrice-Werte von Produkten ab; die Abfrage gibt jedoch den gleichen Alias (Price) für diese beiden Spalten an.</span><span class="sxs-lookup"><span data-stu-id="89ae5-160">For example, the following query retrieves ListPrice and DealerPrice values of products, but the query specifies the same alias, Price, for these two columns.</span></span> <span data-ttu-id="89ae5-161">Aus diesem Grund besitzt das sich ergebende Rowset zwei Spalten mit dem gleichen Namen.</span><span class="sxs-lookup"><span data-stu-id="89ae5-161">Therefore, the resulting rowset will have two columns with same name.</span></span>  
  
### <a name="case-1-both-subelements-are-nonkey-columns-of-the-same-type-and-can-be-null"></a><span data-ttu-id="89ae5-162">Fall 1: Beide Unterelemente sind Nichtschlüsselspalten des gleichen Typs und können den Wert NULL besitzen</span><span class="sxs-lookup"><span data-stu-id="89ae5-162">Case 1: Both subelements are nonkey columns of the same type and can be NULL</span></span>  
 <span data-ttu-id="89ae5-163">In der folgenden Abfrage sind beide Unterelemente Nichtschlüsselspalten des gleichen Typs und können den Wert NULL besitzen.</span><span class="sxs-lookup"><span data-stu-id="89ae5-163">In the following query, both subelements are nonkey columns of the same type and can be NULL.</span></span>  
  
```  
DROP TABLE T  
go  
CREATE TABLE T (ProductID int primary key, ListPrice money, DealerPrice money)  
go  
INSERT INTO T values (1, 1.25, null)  
go  
  
SELECT ProductID, ListPrice Price, DealerPrice Price  
FROM   T  
for    XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="89ae5-164">Dies ist das entsprechende XML, das generiert wird.</span><span class="sxs-lookup"><span data-stu-id="89ae5-164">This is the corresponding XML generated.</span></span> <span data-ttu-id="89ae5-165">Es wird nur ein Teil des XSD-Inlineschemas dargestellt.</span><span class="sxs-lookup"><span data-stu-id="89ae5-165">Only a fraction of the inline XSD is shown:</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" minOccurs="0" maxOccurs="2" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<ProductID>1</ProductID>`  
  
 `<Price>1.2500</Price>`  
  
 `</row>`  
  
 <span data-ttu-id="89ae5-166">Beachten Sie Folgendes bezüglich des XSD-Inlineschemas:</span><span class="sxs-lookup"><span data-stu-id="89ae5-166">Note the following in the inline XSD schema:</span></span>  
  
-   <span data-ttu-id="89ae5-167">ListPrice und DealerPrice sind vom gleichen Datentyp ( `money`), und beide Angaben können in der Tabelle den Wert NULL aufweisen.</span><span class="sxs-lookup"><span data-stu-id="89ae5-167">Both the ListPrice and DealerPrice are of the same type, `money`, and both can be NULL in the table.</span></span> <span data-ttu-id="89ae5-168">Da sie im sich ergebenden XML nicht zurückgegeben werden können, ist nur ein untergeordnetes <`Price`>-Element in der komplexen Typdeklaration des <`row`>-Elements vorhanden, das die Werte "minOccurs=0" und "maxOccurs=2" aufweist.</span><span class="sxs-lookup"><span data-stu-id="89ae5-168">Therefore, because they may not be returned in the resulting XML, there is only one <`Price`> child element in the complex type declaration of the <`row`> element that has minOccurs=0 and maxOccurs=2.</span></span>  
  
-   <span data-ttu-id="89ae5-169">Da der Wert `DealerPrice` in der Tabelle NULL ist, wird nur `ListPrice` als <`Price`>-Element zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="89ae5-169">In the result, because the `DealerPrice` value is NULL in the table, only `ListPrice` is returned as a <`Price`> element.</span></span> <span data-ttu-id="89ae5-170">Wenn Sie der ELEMENTS-Direktive den `XSINIL`-Parameter hinzufügen, erhalten Sie beide Elemente, deren Wert `xsi:nil`für das <`Price`>-Element auf TRUE festgelegt wurde, das DealerPrice entspricht.</span><span class="sxs-lookup"><span data-stu-id="89ae5-170">If you add the `XSINIL` parameter to the ELEMENTS directive, you will receive both of the elements that have the `xsi:nil` value set to TRUE for the<`Price`> element that corresponds to DealerPrice.</span></span> <span data-ttu-id="89ae5-171">Außerdem erhalten Sie zwei untergeordnete <`Price`>-Elemente in der komplexen Typdefinition <`row`> im XSD-Inlineschema, wobei das `nillable`-Attribut für beide auf TRUE festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="89ae5-171">You will also receive two <`Price`> child elements in the <`row`> complex type definition in the inline XSD schema with the `nillable` attribute set to TRUE for both.</span></span> <span data-ttu-id="89ae5-172">Dieses Fragment ist ein Teilergebnis:</span><span class="sxs-lookup"><span data-stu-id="89ae5-172">This fragment is a partial result:</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" nillable="1" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" nillable="1" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" nillable="1" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">`  
  
 `<ProductID>1</ProductID>`  
  
 `<Price>1.2500</Price>`  
  
 `<Price xsi:nil="true" />`  
  
 `</row>`  
  
### <a name="case-2-one-key-and-one-nonkey-column-of-the-same-type"></a><span data-ttu-id="89ae5-173">Fall 2: Eine Schlüssel- und eine Nichtschlüsselspalte des gleichen Typs</span><span class="sxs-lookup"><span data-stu-id="89ae5-173">Case 2: One key and one nonkey column of the same type</span></span>  
 <span data-ttu-id="89ae5-174">Die folgende Abfrage zeigt eine Schlüssel- und eine Nichtschlüsselspalte des gleichen Typs.</span><span class="sxs-lookup"><span data-stu-id="89ae5-174">The following query illustrates one key and one nonkey column of the same type.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 int, Col3 nvarchar(20))  
go  
INSERT INTO T VALUES (1, 1, 'test')  
go   
```  
  
 <span data-ttu-id="89ae5-175">Die folgende Abfrage für die Tabelle **T** gibt den gleichen Alias für Col1 und Col2 an, wobei Col1 ein Primärschlüssel ist und nicht null sein darf, wohingegen Col2 null sein darf.</span><span class="sxs-lookup"><span data-stu-id="89ae5-175">The following query against table **T** specifies the same alias for Col1 and Col2, where Col1 is a primary key and cannot be null, and Col2 can be null.</span></span> <span data-ttu-id="89ae5-176">Diese Abfrage generiert zwei gleichgeordnete Elemente, die untergeordnete Elemente des <`row`>-Elements sind.</span><span class="sxs-lookup"><span data-stu-id="89ae5-176">This generates two sibling elements that are children of the <`row`> element.</span></span>  
  
```  
SELECT Col1 as Col, Col2 as Col, Col3  
FROM T  
FOR XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="89ae5-177">Dies ist das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="89ae5-177">This is the result.</span></span> <span data-ttu-id="89ae5-178">Es wird nur ein Fragment des XSD-Schemas dargestellt.</span><span class="sxs-lookup"><span data-stu-id="89ae5-178">Only a fragment of the inline XSD schema is shown.</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="Col" type="sqltypes:int" />`  
  
 `<xsd:element name="Col" type="sqltypes:int" minOccurs="0" />`  
  
 `<xsd:element name="Col3" minOccurs="0">`  
  
 `<xsd:simpleType>`  
  
 `<xsd:restriction base="sqltypes:nvarchar"`  
  
 `sqltypes:localeId="1033"`  
  
 `sqltypes:sqlCompareOptions="IgnoreCase`  
  
 `IgnoreKanaType IgnoreWidth"`  
  
 `sqltypes:sqlSortId="52">`  
  
 `<xsd:maxLength value="20" />`  
  
 `</xsd:restriction>`  
  
 `</xsd:simpleType>`  
  
 `</xsd:element>`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<Col>1</Col>`  
  
 `<Col>1</Col>`  
  
 `<Col3>test</Col3>`  
  
 `</row>`  
  
 <span data-ttu-id="89ae5-179">Beachten Sie im XSD-Inlineschema, dass für das <`Col`>-Element, das Col2 entspricht, minOccurs auf 0 festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="89ae5-179">Note in the inline XSD schema that the <`Col`> element corresponding to the Col2 has minOccurs set to 0.</span></span>  
  
### <a name="case-3-both-elements-of-different-types-and-corresponding-columns-can-be-null"></a><span data-ttu-id="89ae5-180">Fall 3: Beide Elemente unterschiedlicher Typen und entsprechender Spalten dürfen NULL sein</span><span class="sxs-lookup"><span data-stu-id="89ae5-180">Case 3: Both elements of different types and corresponding columns can be NULL</span></span>  
 <span data-ttu-id="89ae5-181">Die folgende Abfrage wird für die gleiche Tabelle angegeben, die auch in Fall 2 gezeigt wurde:</span><span class="sxs-lookup"><span data-stu-id="89ae5-181">The following query is specified against the sample table shown in case 2:</span></span>  
  
```  
SELECT Col1, Col2 as Col, Col3 as Col  
FROM T  
FOR XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="89ae5-182">In der folgenden Abfrage erhalten Col2 und Col3 den gleichen Alias.</span><span class="sxs-lookup"><span data-stu-id="89ae5-182">In the following query, Col2 and Col3 are given the same aliases.</span></span> <span data-ttu-id="89ae5-183">Diese Abfrage generiert zwei gleichgeordnete Elemente, die den gleichen Namen besitzen und untergeordnete Elemente des <`raw`>-Elements im Ergebnis sind.</span><span class="sxs-lookup"><span data-stu-id="89ae5-183">This generates two sibling elements that have the same name and that are both children of the <`raw`> element in the result.</span></span> <span data-ttu-id="89ae5-184">Diese beiden Spalten gehören unterschiedlichen Typen an und dürfen NULL sein</span><span class="sxs-lookup"><span data-stu-id="89ae5-184">Both of these columns are of different types and both can be NULL.</span></span> <span data-ttu-id="89ae5-185">Dies ist das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="89ae5-185">This is the result.</span></span> <span data-ttu-id="89ae5-186">Es wird nur ein Teil des XSD-Inlineschemas gezeigt.</span><span class="sxs-lookup"><span data-stu-id="89ae5-186">Only partial inline XSD schema is shown.</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:simpleType name="Col1">`  
  
 `<xsd:restriction base="sqltypes:int" />`  
  
 `</xsd:simpleType>`  
  
 `<xsd:simpleType name="Col2">`  
  
 `<xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033"`  
  
 `sqltypes:sqlCompareOptions="IgnoreCase`  
  
 `IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">`  
  
 `<xsd:maxLength value="20" />`  
  
 `</xsd:restriction>`  
  
 `</xsd:simpleType>`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="Col1" type="sqltypes:int" />`  
  
 `<xsd:element name="Col" minOccurs="0" maxOccurs="2" type="xsd:anySimpleType" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<Col1>1</Col1>`  
  
 `<Col xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`  
  
 `xsi:type="Col1">1</Col>`  
  
 `<Col xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`  
  
 `xsi:type="Col2">test</Col>`  
  
 `</row>`  
  
 <span data-ttu-id="89ae5-187">Beachten Sie Folgendes bezüglich des XSD-Inlineschemas:</span><span class="sxs-lookup"><span data-stu-id="89ae5-187">Note the following in the inline XSD schema:</span></span>  
  
-   <span data-ttu-id="89ae5-188">Da sowohl Col2 als auch Col3 NULL sein dürfen, gibt die Deklaration des <`Col`>-Elements minOccurs als 0 und maxOccurs als 2 an.</span><span class="sxs-lookup"><span data-stu-id="89ae5-188">Because both Col2 and Col3 can be NULL, the <`Col`> element declaration specifies the minOccurs as 0 and maxOccurs as 2.</span></span>  
  
-   <span data-ttu-id="89ae5-189">Da beide <`Col`>-Elemente gleichgeordnete Elemente sind, ist im Schema eine Elementdeklaration vorhanden.</span><span class="sxs-lookup"><span data-stu-id="89ae5-189">Because both the <`Col`> elements are siblings, there is one element declaration in the schema.</span></span> <span data-ttu-id="89ae5-190">Da die Elemente unterschiedlichen Typen angehören, obwohl beide Elemente simple-Typen sind, ist der Typ des Elements im Schema `xsd:anySimpleType`.</span><span class="sxs-lookup"><span data-stu-id="89ae5-190">Also, because both of the elements are also of different types, though both are simple types, the type of the element in the schema is `xsd:anySimpleType`.</span></span> <span data-ttu-id="89ae5-191">Im Ergebnis wird jeder Instanztyp durch das `xsi:type` -Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="89ae5-191">In the result, each instance type is identified by the `xsi:type` attribute.</span></span>  
  
-   <span data-ttu-id="89ae5-192">Im Ergebnis verweist jede Instanz des <`Col`>-Elements mithilfe des `xsi:type`-Attributs auf ihren Instanztyp.</span><span class="sxs-lookup"><span data-stu-id="89ae5-192">In the result, every instance of the <`Col`> element refers to its instance type by using the `xsi:type` attribute.</span></span>  
  
  
