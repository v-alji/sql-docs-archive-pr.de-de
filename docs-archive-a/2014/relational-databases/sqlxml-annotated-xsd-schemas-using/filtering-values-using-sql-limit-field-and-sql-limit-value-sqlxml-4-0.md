---
title: "Filtern von Werten mit ' SQL: limit-field ' und ' SQL: limit-value ' (SQLXML 4,0) | Microsoft-Dokumentation"
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, filtering values
- limiting values [SQLXML]
- limit-value annotation
- limit-field annotation
- sql:limit-field
- sql:limit-value
- filtering [SQLXML]
ms.assetid: c0f7ae92-eeec-430e-a66a-f22c3ae64a5e
author: rothja
ms.author: jroth
ms.openlocfilehash: 7886a9a6f51c76ed693576ca6f4659f4051d1f20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725354"
---
# <a name="filtering-values-using-sqllimit-field-and-sqllimit-value-sqlxml-40"></a><span data-ttu-id="e7e5c-102">Filtern von Werten mit 'sql:limit-field' und 'sql:limit-value' (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e7e5c-102">Filtering Values Using sql:limit-field and sql:limit-value (SQLXML 4.0)</span></span>
  <span data-ttu-id="e7e5c-103">Sie können Zeilen, die von einer Datenbankabfrage zurückgegeben werden, mit einem Grenzwert beschränken.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-103">You can limit rows that are returned from a database query on the basis of some limiting value.</span></span> <span data-ttu-id="e7e5c-104">Mithilfe der `sql:limit-field`- und der `sql:limit-value`-Anmerkung können Sie die Datenbankspalte, die die Grenzwerte enthält, identifizieren und einen bestimmten Grenzwert angeben, der zum Filtern der zurückgegebenen Daten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-104">The `sql:limit-field` and `sql:limit-value` annotations are used to identify the database column that contains limiting values and to specify a specific limiting value to be used to filter the data returned.</span></span>  
  
 <span data-ttu-id="e7e5c-105">Mithilfe der `sql:limit-field`-Anmerkung können Sie eine Spalte identifizieren, die einen Grenzwert enthält. Dies ist für alle zugeordneten Elemente oder Attribute zulässig.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-105">The `sql:limit-field` annotation is used to identify a column that contains a limiting value; it is allowed on each mapped element or attribute.</span></span>  
  
 <span data-ttu-id="e7e5c-106">Die-Anmerkung `sql:limit-value` wird verwendet, um den begrenzten Wert in der Spalte anzugeben, die in der-Anmerkung angegeben wird `sql:limit-field` .</span><span class="sxs-lookup"><span data-stu-id="e7e5c-106">The `sql:limit-value` annotation is used to specify the limited value in the column that is specified in the `sql:limit-field` annotation.</span></span> <span data-ttu-id="e7e5c-107">Die `sql:limit-value`-Anmerkung ist optional.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-107">The `sql:limit-value` annotation is optional.</span></span> <span data-ttu-id="e7e5c-108">Wenn `sql:limit-value` nicht angegeben wird, wird ein NULL-Wert angenommen.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-108">If `sql:limit-value` is not specified, a NULL value is assumed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7e5c-109">Bei Verwendung einer `sql:limit-field`-Anmerkung, bei der die zugeordnete SQL-Spalte eine Spalte vom Typ `real` ist, konvertiert SQLXML 4.0 die `sql:limit-value`-Anmerkung wie in XML-Schemas angegeben in einen angegebenen `nvarchar`-Wert.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-109">When working with a `sql:limit-field` where the mapped SQL column is of type `real`, SQLXML 4.0 performs conversion on the `sql:limit-value` as specified in XML schemas as an `nvarchar` specified value.</span></span> <span data-ttu-id="e7e5c-110">Hierzu müssen Dezimalgrenzwerte mithilfe der vollständigen wissenschaftlichen Schreibweise angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-110">This requires that decimal limit values be specified using full scientific notation.</span></span> <span data-ttu-id="e7e5c-111">Weitere Informationen finden Sie im Folgenden unter Beispiel B.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-111">For more information, see Example B below.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e7e5c-112">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e7e5c-112">Examples</span></span>  
 <span data-ttu-id="e7e5c-113">Um mithilfe dieser Daten funktionstüchtige Beispiele zu erstellen, muss Folgendes installiert sein:</span><span class="sxs-lookup"><span data-stu-id="e7e5c-113">To create working samples using these examples, you need to have the following installed:</span></span>  
  
-   <span data-ttu-id="e7e5c-114">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="e7e5c-114">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span></span>  
  
-   <span data-ttu-id="e7e5c-115">MDAC 2.6 oder höher</span><span class="sxs-lookup"><span data-stu-id="e7e5c-115">MDAC 2.6 or later</span></span>  
  
 <span data-ttu-id="e7e5c-116">In diesen Beispielen werden mithilfe der Vorlagen XPath-Abfragen für das XSD-Zuordnungsschema angegeben.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-116">In these examples, templates are used to specify XPath queries against the mapping XSD schema.</span></span>  
  
### <a name="a-limiting-the-customer-addresses-returned-to-a-specific-address-type"></a><span data-ttu-id="e7e5c-117">A.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-117">A.</span></span> <span data-ttu-id="e7e5c-118">Beschränken der zurückgegebenen Kundenadressen auf einen bestimmten Adresstyp</span><span class="sxs-lookup"><span data-stu-id="e7e5c-118">Limiting the customer addresses returned to a specific address type</span></span>  
 <span data-ttu-id="e7e5c-119">In diesem Beispiel enthält eine Datenbank zwei Tabellen:</span><span class="sxs-lookup"><span data-stu-id="e7e5c-119">In this example, a database contains two tables:</span></span>  
  
-   <span data-ttu-id="e7e5c-120">Customer (CustomerID, CompanyName)</span><span class="sxs-lookup"><span data-stu-id="e7e5c-120">Customer (CustomerID, CompanyName)</span></span>  
  
-   <span data-ttu-id="e7e5c-121">Addresses (CustomerID, AddressType, StreetAddress)</span><span class="sxs-lookup"><span data-stu-id="e7e5c-121">Addresses (CustomerID, AddressType, StreetAddress)</span></span>  
  
 <span data-ttu-id="e7e5c-122">Ein Kunde kann eine Liefer- und/oder eine Rechnungsadresse haben.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-122">A customer can have a shipping address and/or a billing address.</span></span> <span data-ttu-id="e7e5c-123">Die AddressType-Spaltenwerte sind Shipping (Lieferadresse) und Billing (Rechnungsadresse).</span><span class="sxs-lookup"><span data-stu-id="e7e5c-123">The AddressType column values are Shipping and Billing.</span></span>  
  
 <span data-ttu-id="e7e5c-124">Dies ist das Zuordnungs Schema, in dem das **ShipTo** -Schema Attribut der Spalte "StreetAddress" in der Beziehung "Adressen" zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-124">This is the mapping schema in which the **ShipTo** schema attribute maps to the StreetAddress column in the Addresses relation.</span></span> <span data-ttu-id="e7e5c-125">Die Werte, die für dieses Attribut zurückgegeben werden, sind nur durch Angabe der `sql:limit-field` -und-Anmerkungen auf das Versenden von Adressen beschränkt `sql:limit-value` .</span><span class="sxs-lookup"><span data-stu-id="e7e5c-125">The values that are returned for this attribute are limited to only shipping addresses by specifying the `sql:limit-field` and `sql:limit-value` annotations.</span></span> <span data-ttu-id="e7e5c-126">Ebenso gibt das Attribut " **BillTo** Schema" nur die Abrechnungsadresse eines Kunden zurück.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-126">Similarly, the **BillTo** schema attribute returns only the billing address of a customer.</span></span>  
  
 <span data-ttu-id="e7e5c-127">Das ist das Schema:</span><span class="sxs-lookup"><span data-stu-id="e7e5c-127">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustAddr"  
        parent="Customer"  
        parent-key="CustomerID"  
        child="Addresses"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Customer" >  
   <xsd:complexType>  
        <xsd:sequence>  
        <xsd:element name="BillTo"   
                       type="xsd:string"   
                       sql:relation="Addresses"   
                       sql:field="StreetAddress"  
                       sql:limit-field="AddressType"  
                       sql:limit-value="billing"  
                       sql:relationship="CustAddr" >  
        </xsd:element>  
        <xsd:element name="ShipTo"   
                       type="xsd:string"   
                       sql:relation="Addresses"   
                       sql:field="StreetAddress"  
                       sql:limit-field="AddressType"  
                       sql:limit-value="shipping"  
                       sql:relationship="CustAddr" >  
        </xsd:element>  
        </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:int" />   
        <xsd:attribute name="CompanyName"  type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e7e5c-128">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="e7e5c-128">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e7e5c-129">Erstellen Sie zwei Tabellen in der **tempdb** -Datenbank:</span><span class="sxs-lookup"><span data-stu-id="e7e5c-129">Create two tables in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Customer (CustomerID int primary key,   
                           CompanyName varchar(30))  
    CREATE TABLE Addresses(CustomerID int,   
                           StreetAddress varchar(50),  
                           AddressType varchar(10))  
    ```  
  
2.  <span data-ttu-id="e7e5c-130">Fügen Sie die Beispieldaten hinzu:</span><span class="sxs-lookup"><span data-stu-id="e7e5c-130">Add the sample data:</span></span>  
  
    ```  
    INSERT INTO Customer values (1, 'Company A')  
    INSERT INTO Customer values (2, 'Company B')  
  
    INSERT INTO Addresses values  
               (1, 'Obere Str. 57 Berlin', 'billing')  
    INSERT INTO Addresses values  
               (1, 'Avda. de la Constituci??n 2222 M??xico D.F.', 'shipping')  
    INSERT INTO Addresses values  
               (2, '120 Hanover Sq., London', 'billing')  
    INSERT INTO Addresses values  
               (2, 'Forsterstr. 57, Mannheim', 'shipping')  
    ```  
  
3.  <span data-ttu-id="e7e5c-131">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-131">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="e7e5c-132">Speichern Sie die Datei unter dem Dateinamen LimitFieldValue.xml.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-132">Save the file as LimitFieldValue.xml.</span></span>  
  
4.  <span data-ttu-id="e7e5c-133">Erstellen Sie die folgende Vorlage (LimitFieldValueT.xml), und speichern Sie sie dort, wo Sie im vorherigen Schritt auch das Schema (LimitFieldValue.xml) gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-133">Create the following template (LimitFieldValueT.xml), and save it in the same where you saved the schema (LimitFieldValue.xml) in the previous step:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="LimitFieldValue.xml">  
            /Customer  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e7e5c-134">Der für das Zuordnungsschema (LimitFieldValue.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-134">The directory path specified for the mapping schema (LimitFieldValue.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e7e5c-135">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e7e5c-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\LimitFieldValue.xml"  
    ```  
  
5.  <span data-ttu-id="e7e5c-136">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e7e5c-137">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e7e5c-137">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e7e5c-138">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="e7e5c-138">This is the result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer CustomerID="1" CompanyName="Company A">   
     <BillTo>Obere Str. 57 Berlin</BillTo>   
     <ShipTo>Avda. de la Constituci??n 2222 M??xico D.F.</ShipTo>   
  </Customer>   
  <Customer CustomerID="2" CompanyName="Company B">   
     <BillTo>120 Hanover Sq., London</BillTo>   
     <ShipTo>Forsterstr. 57, Mannheim</ShipTo>   
   </Customer>   
</ROOT>  
```  
  
### <a name="b-limiting-results-based-on-a-discount-value-of-type-real-data"></a><span data-ttu-id="e7e5c-139">B.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-139">B.</span></span> <span data-ttu-id="e7e5c-140">Beschränken von Ergebnissen anhand eines Rabattwerts vom Datentyp "real"</span><span class="sxs-lookup"><span data-stu-id="e7e5c-140">Limiting results based on a discount value of type real data</span></span>  
 <span data-ttu-id="e7e5c-141">In diesem Beispiel enthält eine Datenbank zwei Tabellen:</span><span class="sxs-lookup"><span data-stu-id="e7e5c-141">In this example, a database contains two tables:</span></span>  
  
-   <span data-ttu-id="e7e5c-142">Orders (OrderID)</span><span class="sxs-lookup"><span data-stu-id="e7e5c-142">Orders (OrderID)</span></span>  
  
-   <span data-ttu-id="e7e5c-143">OrderDetails (OrderID, ProductID, UnitPrice, Quantity, Price, Discount)</span><span class="sxs-lookup"><span data-stu-id="e7e5c-143">OrderDetails (OrderID, ProductID, UnitPrice, Quantity, Price, Discount)</span></span>  
  
 <span data-ttu-id="e7e5c-144">Dies ist das Zuordnungs Schema, in dem das **OrderID** -Attribut in den Bestelldetails der OrderID-Spalte in der Orders-Beziehung zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-144">This is the mapping schema in which the **OrderID** attribute on the order details maps to the OrderID column in the orders relation.</span></span> <span data-ttu-id="e7e5c-145">Die Werte, die für dieses Attribut zurückgegeben werden, sind auf die Werte beschränkt, die den Wert 0000000e e-001 (0,2) aufweisen, wie für das **Discount** -Attribut mithilfe der `sql:limit-field` -und-Anmerkungen angegeben `sql:limit-value` .</span><span class="sxs-lookup"><span data-stu-id="e7e5c-145">The values that are returned for this attribute are limited to only those that have a value of 2.0000000e-001 (0.2) as specified for the **Discount** attribute using the `sql:limit-field` and `sql:limit-value` annotations.</span></span>  
  
 <span data-ttu-id="e7e5c-146">Das ist das Schema:</span><span class="sxs-lookup"><span data-stu-id="e7e5c-146">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
   <xsd:appinfo>  
    <sql:relationship name="OrderOrderDetails"  
        parent="Orders"  
        parent-key="OrderID"  
        child="OrderDetails"  
        child-key="OrderID" />  
   </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="root" sql:is-constant="1">  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="Order" sql:relation="Orders" >  
          <xsd:complexType>  
             <xsd:sequence>  
                <xsd:element name="orderDetail"   
                       sql:relation="OrderDetails"   
                       sql:limit-field="Discount"                       sql:limit-value="2.0000000e-001"  
                       sql:relationship="OrderOrderDetails">  
                   <xsd:complexType>  
                     <xsd:attribute name="OrderID"   />   
                     <xsd:attribute name="ProductID" />   
                     <xsd:attribute name="Discount"  />   
                     <xsd:attribute name="Quantity"  />   
                     <xsd:attribute name="UnitPrice" />   
                   </xsd:complexType>  
                </xsd:element>  
            </xsd:sequence>  
           <xsd:attribute name="OrderID"/>   
          </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
   </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e7e5c-147">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="e7e5c-147">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e7e5c-148">Erstellen Sie zwei Tabellen in der **tempdb** -Datenbank:</span><span class="sxs-lookup"><span data-stu-id="e7e5c-148">Create two tables in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Orders ([OrderID] int NOT NULL ) ON [PRIMARY]  
    ALTER TABLE Orders WITH NOCHECK ADD   
    CONSTRAINT [PK_Orders] PRIMARY KEY  CLUSTERED (  
       [OrderID]  
     )  ON [PRIMARY]   
    CREATE TABLE [OrderDetails] (  
       [OrderID] int NOT NULL ,  
       [ProductID] int NOT NULL ,  
       [UnitPrice] money NULL ,  
       [Quantity] smallint NOT NULL ,  
       [Discount] real NOT NULL   
    ) ON [PRIMARY]  
    ```  
  
2.  <span data-ttu-id="e7e5c-149">Fügen Sie die Beispieldaten hinzu:</span><span class="sxs-lookup"><span data-stu-id="e7e5c-149">Add the sample data:</span></span>  
  
    ```  
    INSERT INTO Orders ([OrderID]) values (10248)  
    INSERT INTO Orders ([OrderID]) values (10250)  
    INSERT INTO Orders ([OrderID]) values (10251)  
    INSERT INTO Orders ([OrderID]) values (10257)  
    INSERT INTO Orders ([OrderID]) values (10258)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10248,11,14,12,0)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10250,51,42.4,35,0.15)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10251,22,16.8,6,0.05)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10257,77,10.4,15,0)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10258,2,15.2,50,0.2)  
    ```  
  
3.  <span data-ttu-id="e7e5c-150">Speichern Sie das Schema (LimitFieldValue.xml) in einem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-150">Save the schema (LimitFieldValue.xml) in a directory.</span></span>  
  
4.  <span data-ttu-id="e7e5c-151">Erstellen Sie das folgende Testskript (TestQuery.vbs), geben Sie anstelle von MyServer den Namen des SQL Server-Computers ein, und speichern Sie das Skript in dem Verzeichnis, in dem Sie im vorherigen Schritt das Schema gespeichert haben:</span><span class="sxs-lookup"><span data-stu-id="e7e5c-151">Create the following test script (TestQuery.vbs), modify MyServer to the name of your SQL Server computer and save it in the same directory as you used in the previous step to save the schema:</span></span>  
  
    ```  
    Set conn = CreateObject("ADODB.Connection")  
    conn.Open "Provider=SQLOLEDB;Data Source=MyServer;Database=tempdb;Integrated Security=SSPI"  
    conn.Properties("SQLXML Version") = "sqlxml.4.0"   
    Set cmd = CreateObject("ADODB.Command")  
    Set stm = CreateObject("ADODB.Stream")  
    Set cmd.ActiveConnection = conn  
    stm.open  
    result ="none"  
    strXPathQuery="/root"  
    DBGUID_XPATH = "{EC2A4293-E898-11D2-B1B7-00C04F680C56}"  
    cmd.Dialect = DBGUID_XPATH  
    cmd.CommandText = strXPathQuery  
    cmd.Properties("Mapping schema") = "LimitFieldReal.xml"  
    cmd.Properties("Output Stream").Value = stm  
    cmd.Properties("Output Encoding") = "utf-8"  
    WScript.Echo "executing for xml query"  
    On Error Resume Next  
    cmd.Execute , ,1024  
    if err then  
    Wscript.Echo err.description  
    Wscript.Echo err.Number  
    Wscript.Echo err.source  
    On Error GoTo 0  
    else  
    stm.Position = 0  
    result  = stm.ReadText  
    end if  
    WScript.Echo result  
    Wscript.Echo "done"  
    ```  
  
5.  <span data-ttu-id="e7e5c-152">Führen Sie die Datei TestQuery.vbs aus, indem Sie in Windows Explorer auf die Datei klicken.</span><span class="sxs-lookup"><span data-stu-id="e7e5c-152">Execute the TestQuery.vbs file by clicking on it in Windows Explorer.</span></span>  
  
     <span data-ttu-id="e7e5c-153">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="e7e5c-153">This is the result:</span></span>  
  
    ```  
    <root>  
      <Order OrderID="10248"/>  
      <Order OrderID="10250"/>  
      <Order OrderID="10251"/>  
      <Order OrderID="10257"/>  
      <Order OrderID="10258">  
        <orderDetail OrderID="10258"   
                     ProductID="2"   
                     Discount="0.2"   
                     Quantity="50"/>  
      </Order>  
    </root>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e7e5c-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7e5c-154">See Also</span></span>  
 <span data-ttu-id="e7e5c-155">[float und Real &#40;Transact-SQL-&#41;](/sql/t-sql/data-types/float-and-real-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7e5c-155">[float and real &#40;Transact-SQL&#41;](/sql/t-sql/data-types/float-and-real-transact-sql) </span></span>  
 <span data-ttu-id="e7e5c-156">[nchar und nvarchar &#40;Transact-SQL-&#41;](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7e5c-156">[nchar and nvarchar &#40;Transact-SQL&#41;](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql) </span></span>  
 <span data-ttu-id="e7e5c-157">[Installieren von SQL Server Native Client](../../relational-databases/native-client/applications/installing-sql-server-native-client.md) </span><span class="sxs-lookup"><span data-stu-id="e7e5c-157">[Installing SQL Server Native Client](../../relational-databases/native-client/applications/installing-sql-server-native-client.md) </span></span>  
 [<span data-ttu-id="e7e5c-158">Verwenden von XSD-Schemas mit Anmerkungen in Abfragen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e7e5c-158">Using Annotated XSD Schemas in Queries &#40;SQLXML 4.0&#41;</span></span>](../../relational-databases/sqlxml/annotated-xsd-schemas/using-annotated-xsd-schemas-in-queries-sqlxml-4-0.md)  
  
  
