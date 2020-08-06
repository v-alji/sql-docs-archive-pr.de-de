---
title: Beispiele für XML-Massen laden (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- overflow-field annotation
- ConnectionCommand property
- XMLFragment property
- relationship chains [SQLXML]
- multiple table bulk loading
- examples [SQLXML], XML Bulk Load
- overflow data [SQLXML]
- sql:datatype
- transaction mode [SQLXML]
- CheckConstraints property
- sql:overflow-field
- XML Bulk Load [SQLXML], examples
- TempFilePath property
- datatype annotation
- Transaction property
- KeepIdentity property
- Execute method
- streaming XML data
- xml data type [SQL Server], SQLXML
- bulk load [SQLXML], examples
ms.assetid: 970e4553-b41d-4a12-ad50-0ee65d1f305d
author: rothja
ms.author: jroth
ms.openlocfilehash: c7eaec77ef068efd28c4da65833afa5047b222f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695489"
---
# <a name="xml-bulk-load-examples-sqlxml-40"></a><span data-ttu-id="68abd-102">Beispiele für XML-Massenladen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="68abd-102">XML Bulk Load Examples (SQLXML 4.0)</span></span>
  <span data-ttu-id="68abd-103">In den folgenden Beispielen wird das XML-Massenladen in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="68abd-103">The following examples illustrate the XML Bulk Load functionality in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="68abd-104">Alle Beispiele enthalten ein XSD-Schema und das entsprechende XDR-Schema.</span><span class="sxs-lookup"><span data-stu-id="68abd-104">Each example provides an XSD schema and its equivalent XDR schema.</span></span>  
  
## <a name="bulk-loader-script-validateandbulkloadvbs"></a><span data-ttu-id="68abd-105">Skript für das Massenladen (ValidateAndBulkload.vbs)</span><span class="sxs-lookup"><span data-stu-id="68abd-105">Bulk Loader Script (ValidateAndBulkload.vbs)</span></span>  
 <span data-ttu-id="68abd-106">Das folgende Skript, das in der [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) geschrieben wurde, lädt ein XML-Dokument in das XML-DOM, überprüft es anhand eines Schemas und führt, wenn das Dokument gültig ist, einen XML-Massen Ladevorgang aus, um den XML-Code in eine Tabelle zu laden [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="68abd-106">The following script, written in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript), loads an XML document into the XML DOM; validates it against a schema; and, if the document is valid, executes an XML bulk load to load the XML into a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="68abd-107">Dieses Skript kann mit allen Beispielen in diesem Kapitel ausgeführt werden, die einen entsprechenden Verweis enthalten.</span><span class="sxs-lookup"><span data-stu-id="68abd-107">This script can be used with each of the individual examples that refer to it later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68abd-108">Der XML-Massenladevorgang gibt keine Warnung aus, wenn kein Inhalt von der Datendatei hochgeladen wird.</span><span class="sxs-lookup"><span data-stu-id="68abd-108">XML Bulk Load does not throw a warning or an error if no content is uploaded from the data file.</span></span> <span data-ttu-id="68abd-109">Es wird daher empfohlen, die XML-Datendatei vor dem Ausführen eines Massenladevorgangs zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="68abd-109">Therefore, it is a good practice to validate your XML data file prior to executing a bulk load operation.</span></span>  
  
```  
Dim FileValid  
  
set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=MyServer;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
  
'Validate the data file prior to bulkload  
Dim sOutput   
sOutput = ValidateFile("SampleXMLData.xml", "", "SampleSchema.xml")  
WScript.Echo sOutput  
  
If FileValid Then  
   ' Check constraints and initiate transaction (if needed)  
   ' objBL.CheckConstraints = True  
   ' objBL.Transaction=True  
  'Execute XML bulkload using file.  
  objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
  set objBL=Nothing  
End If  
  
Function ValidateFile(strXmlFile,strUrn,strXsdFile)  
  
   ' Create a schema cache and add SampleSchema.xml to it.  
   Dim xs, fso, sAppPath  
   Set fso = CreateObject("Scripting.FileSystemObject")   
   Set xs = CreateObject("MSXML2.XMLSchemaCache.6.0")  
   sAppPath = fso.GetFolder(".")   
   xs.Add strUrn, sAppPath & "\" & strXsdFile  
  
   ' Create an XML DOMDocument object.  
   Dim xd   
   Set xd = CreateObject("MSXML2.DOMDocument.6.0")  
  
   ' Assign the schema cache to the DOM document.  
   ' schemas collection.  
   Set xd.schemas = xs  
  
   ' Load XML document as DOM document.  
   xd.async = False  
   xd.Load sAppPath & "\" & strXmlFile  
  
   ' Return validation results in message to the user.  
   If xd.parseError.errorCode <> 0 Then  
        ValidateFile = "Validation failed on " & _  
             strXmlFile & vbCrLf & _  
             "=======" & vbCrLf & _  
             "Reason: " & xd.parseError.reason & _  
             vbCrLf & "Source: " & _  
             xd.parseError.srcText & _  
             vbCrLf & "Line: " & _  
             xd.parseError.Line & vbCrLf  
             FileValid = False  
    Else  
        ValidateFile = "Validation succeeded for " & _  
             strXmlFile & vbCrLf & _  
             "========" & _  
             vbCrLf & "Contents to be bulkloaded" & vbCrLf  
             FileValid = True  
    End If  
End Function  
```  
  
## <a name="a-bulk-loading-xml-in-a-table"></a><span data-ttu-id="68abd-110">A.</span><span class="sxs-lookup"><span data-stu-id="68abd-110">A.</span></span> <span data-ttu-id="68abd-111">Massenladen von XML-Daten in eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="68abd-111">Bulk loading XML in a table</span></span>  
 <span data-ttu-id="68abd-112">Dieses Beispiel stellt eine Verbindung mit der Instanz von her [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , die in der ConnectionString-Eigenschaft (MyServer) angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="68abd-112">This example establishes a connection to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is specified in the ConnectionString property (MyServer).</span></span> <span data-ttu-id="68abd-113">Im Beispiel wird auch die ErrorLogFile-Eigenschaft angegeben.</span><span class="sxs-lookup"><span data-stu-id="68abd-113">The example also specifies the ErrorLogFile property.</span></span> <span data-ttu-id="68abd-114">Daher wird die Fehlerausgabe in der angegebenen Datei (C:\error.log) gespeichert. Sie können den Speicherort auch jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="68abd-114">Therefore, the error output is saved in the specified file ("C:\error.log"), which you might also decide to change to a different location.</span></span> <span data-ttu-id="68abd-115">Beachten Sie auch, dass die Execute-Methode als Parameter sowohl die Mapping-Schema Datei (SampleSchema.xml) als auch die XML-Datendatei (SampleXMLData.xml) aufweist.</span><span class="sxs-lookup"><span data-stu-id="68abd-115">Notice also that the Execute method has as its parameters both the mapping schema file (SampleSchema.xml) and the XML data file (SampleXMLData.xml).</span></span> <span data-ttu-id="68abd-116">Wenn der Massen Ladevorgang ausgeführt wird, enthält die Cust-Tabelle, die Sie in der **tempdb** -Datenbank erstellt haben, neue Datensätze basierend auf dem Inhalt der XML-Datendatei.</span><span class="sxs-lookup"><span data-stu-id="68abd-116">When the bulk load executes, the Cust table you have created in **tempdb** database will contain new records based upon the contents of the XML data file.</span></span>  
  
#### <a name="to-test-a-sample-bulk-load"></a><span data-ttu-id="68abd-117">So testen Sie ein Beispiel für einen Massenladevorgang</span><span class="sxs-lookup"><span data-stu-id="68abd-117">To test a sample bulk load</span></span>  
  
1.  <span data-ttu-id="68abd-118">Erstellen Sie die folgende Tabelle:</span><span class="sxs-lookup"><span data-stu-id="68abd-118">Create this table:</span></span>  
  
    ```  
    CREATE TABLE Cust(CustomerID  int PRIMARY KEY,  
                      CompanyName varchar(20),  
                      City        varchar(20));  
    GO  
    ```  
  
2.  <span data-ttu-id="68abd-119">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-119">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="68abd-120">Fügen Sie dieser Datei das folgende XSD-Schema hinzu:</span><span class="sxs-lookup"><span data-stu-id="68abd-120">To this file, add the following XSD schema:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
       <xsd:element name="ROOT" sql:is-constant="1" >  
         <xsd:complexType>  
           <xsd:sequence>  
             <xsd:element name="Customers" sql:relation="Cust" maxOccurs="unbounded">  
               <xsd:complexType>  
                 <xsd:sequence>  
                   <xsd:element name="CustomerID"  type="xsd:integer" />  
                   <xsd:element name="CompanyName" type="xsd:string" />  
                   <xsd:element name="City"        type="xsd:string" />  
                 </xsd:sequence>  
               </xsd:complexType>  
             </xsd:element>  
           </xsd:sequence>  
          </xsd:complexType>  
         </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="68abd-121">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-121">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="68abd-122">Fügen Sie dieser Datei das folgende XML-Dokument hinzu:</span><span class="sxs-lookup"><span data-stu-id="68abd-122">To this file, add the following XML document:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Sean Chai</CompanyName>  
        <City>New York</City>  
      </Customers>  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Tom Johnston</CompanyName>  
         <City>Los Angeles</City>  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Institute of Art</CompanyName>  
        <City>Chicago</City>  
      </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="68abd-123">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="68abd-123">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="68abd-124">Fügen Sie zu dieser Datei den VBScript-Code hinzu, der am Anfang dieses Themas bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="68abd-124">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="68abd-125">Ändern Sie die Verbindungszeichenfolge, um den entsprechenden Servernamen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="68abd-125">Modify the connection string to provide the appropriate server name.</span></span> <span data-ttu-id="68abd-126">Geben Sie den entsprechenden Pfad für die Dateien an, die als Parameter für die Execute-Methode angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="68abd-126">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
5.  <span data-ttu-id="68abd-127">Führen Sie den VBScript-Code aus.</span><span class="sxs-lookup"><span data-stu-id="68abd-127">Execute the VBScript code.</span></span> <span data-ttu-id="68abd-128">XML-Massenladen lädt den XML-Code in die Cust-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="68abd-128">XML Bulk Load loads the XML into the Cust table.</span></span>  
  
 <span data-ttu-id="68abd-129">Dies ist das entsprechende XDR-Schema:</span><span class="sxs-lookup"><span data-stu-id="68abd-129">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers"  sql:relation="Cust" >  
      <element type="CustomerID"  sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City"        sql:field="City" />  
  
   </ElementType>  
</Schema>  
```  
  
## <a name="b-bulk-loading-xml-data-in-multiple-tables"></a><span data-ttu-id="68abd-130">B.</span><span class="sxs-lookup"><span data-stu-id="68abd-130">B.</span></span> <span data-ttu-id="68abd-131">Massenladen von XML-Daten in mehrere Tabellen</span><span class="sxs-lookup"><span data-stu-id="68abd-131">Bulk loading XML data in multiple tables</span></span>  
 <span data-ttu-id="68abd-132">In diesem Beispiel besteht das XML-Dokument aus den **\<Customer>** **\<Order>** Elementen und.</span><span class="sxs-lookup"><span data-stu-id="68abd-132">In this example, the XML document consists of the **\<Customer>** and **\<Order>** elements.</span></span>  
  
```  
<ROOT>  
  <Customers>  
    <CustomerID>1111</CustomerID>  
    <CompanyName>Sean Chai</CompanyName>  
    <City>NY</City>  
    <Order OrderID="1" />  
    <Order OrderID="2" />  
  </Customers>  
  <Customers>  
    <CustomerID>1112</CustomerID>  
    <CompanyName>Tom Johnston</CompanyName>  
     <City>LA</City>    
    <Order OrderID="3" />  
  </Customers>  
  <Customers>  
    <CustomerID>1113</CustomerID>  
    <CompanyName>Institute of Art</CompanyName>  
    <Order OrderID="4" />  
  </Customers>  
</ROOT>  
```  
  
 <span data-ttu-id="68abd-133">In diesem Beispiel werden die XML-Daten per Massen Vorgang in zwei Tabellen geladen: **cust** und **CustOrder**:</span><span class="sxs-lookup"><span data-stu-id="68abd-133">This example bulk loads the XML data into two tables, **Cust** and **CustOrder**:</span></span>  
  
```  
Cust(CustomerID, CompanyName, City)  
CustOrder(OrderID, CustomerID)  
```  
  
 <span data-ttu-id="68abd-134">Das folgende XSD-Schema definiert die XML-Ansicht für diese Tabellen.</span><span class="sxs-lookup"><span data-stu-id="68abd-134">The following XSD schema defines the XML view of these tables.</span></span> <span data-ttu-id="68abd-135">Das Schema gibt die über-/Unterordnungsbeziehung zwischen den- **\<Customer>** und- **\<Order>** Elementen an.</span><span class="sxs-lookup"><span data-stu-id="68abd-135">The schema specifies the parent-child relationship between the **\<Customer>** and **\<Order>** elements.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="CustCustOrder"  
          parent="Cust"  
          parent-key="CustomerID"  
          child="CustOrder"  
          child-key="CustomerID" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="ROOT" sql:is-constant="1" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Customers" sql:relation="Cust" >  
          <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="CustomerID"  type="xsd:integer" />  
              <xsd:element name="CompanyName" type="xsd:string" />  
              <xsd:element name="City"        type="xsd:string" />  
              <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
                <xsd:complexType>  
                  <xsd:attribute name="OrderID" type="xsd:integer" />  
                </xsd:complexType>  
              </xsd:element>  
             </xsd:sequence>  
          </xsd:complexType>  
        </xsd:element>  
      </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="68abd-136">XML-Massen Laden verwendet die oben angegebene Primärschlüssel/Fremdschlüssel Beziehung zwischen dem **\<Cust>** -Element und dem- **\<CustOrder>** Element, um die Daten per Massen Vorgang in beide Tabellen zu laden.</span><span class="sxs-lookup"><span data-stu-id="68abd-136">XML Bulk Load uses the primary key/foreign key relationship specified above between the **\<Cust>** and **\<CustOrder>** elements to bulk load the data into both tables.</span></span>  
  
#### <a name="to-test-a-sample-bulk-load"></a><span data-ttu-id="68abd-137">So testen Sie ein Beispiel für einen Massenladevorgang</span><span class="sxs-lookup"><span data-stu-id="68abd-137">To test a sample bulk load</span></span>  
  
1.  <span data-ttu-id="68abd-138">Erstellen Sie zwei Tabellen in der **tempdb** -Datenbank:</span><span class="sxs-lookup"><span data-stu-id="68abd-138">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust(  
           CustomerID  int PRIMARY KEY,  
           CompanyName varchar(20),  
           City        varchar(20));  
    CREATE TABLE CustOrder(        OrderID     int PRIMARY KEY,   
            CustomerID int FOREIGN KEY REFERENCES Cust(CustomerID));  
    ```  
  
2.  <span data-ttu-id="68abd-139">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-139">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="68abd-140">Fügen Sie der Datei das XSD-Schema hinzu, das in diesem Beispiel bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="68abd-140">Add the XSD schema that is provided in this example to the file.</span></span>  
  
3.  <span data-ttu-id="68abd-141">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleData.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-141">Create a file in your preferred text or XML editor, and save it as SampleData.xml.</span></span> <span data-ttu-id="68abd-142">Fügen Sie der Datei das XML-Dokument hinzu, das weiter oben in diesem Beispiel bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="68abd-142">Add the XML document that was provided earlier in this example to the file.</span></span>  
  
4.  <span data-ttu-id="68abd-143">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="68abd-143">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="68abd-144">Fügen Sie zu dieser Datei den VBScript-Code hinzu, der am Anfang dieses Themas bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="68abd-144">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="68abd-145">Ändern Sie die Verbindungszeichenfolge, um den entsprechenden Server- und Datenbanknamen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="68abd-145">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="68abd-146">Geben Sie den entsprechenden Pfad für die Dateien an, die als Parameter für die Execute-Methode angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="68abd-146">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
5.  <span data-ttu-id="68abd-147">Führen Sie den oben angegebenen VBScript-Code aus.</span><span class="sxs-lookup"><span data-stu-id="68abd-147">Execute the VBScript code above.</span></span> <span data-ttu-id="68abd-148">XML-Massenladen lädt das XML-Dokument in die Tabellen Cust und CustOrder.</span><span class="sxs-lookup"><span data-stu-id="68abd-148">XML Bulk Load loads the XML document into the Cust and CustOrder tables.</span></span>  
  
 <span data-ttu-id="68abd-149">Dies ist das entsprechende XDR-Schema:</span><span class="sxs-lookup"><span data-stu-id="68abd-149">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust" >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
<sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
</Schema>  
```  
  
## <a name="c-using-chain-relationships-in-the-schema-to-bulk-load-xml"></a><span data-ttu-id="68abd-150">C.</span><span class="sxs-lookup"><span data-stu-id="68abd-150">C.</span></span> <span data-ttu-id="68abd-151">Verwenden von Kettenbeziehungen im Schema für das XML-Massenladen</span><span class="sxs-lookup"><span data-stu-id="68abd-151">Using chain relationships in the schema to bulk load XML</span></span>  
 <span data-ttu-id="68abd-152">Dieses Beispiel zeigt, wie die im Zuordnungsschema festgelegte M:N-Beziehung des XML-Massenladevorgangs zum Laden von Daten in eine Tabelle verwendet wird, die eine M:N-Beziehung darstellt.</span><span class="sxs-lookup"><span data-stu-id="68abd-152">This example illustrates how the M:N relationship that is specified in the mapping schema is used by XML Bulk Load to load data in a table that represents an M:N relationship.</span></span>  
  
 <span data-ttu-id="68abd-153">Das folgende XSD-Schema ist ein Beispiel dafür:</span><span class="sxs-lookup"><span data-stu-id="68abd-153">For example, consider this XSD schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrderOD"  
          parent="Ord"  
          parent-key="OrderID"  
          child="OrderDetail"  
          child-key="OrderID" />  
  
    <sql:relationship name="ODProduct"  
          parent="OrderDetail"  
          parent-key="ProductID"  
          child="Product"  
          child-key="ProductID"   
          inverse="true"/>  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="ROOT" sql:is-constant="1" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Ord"   
                     sql:key-fields="OrderID" >  
          <xsd:complexType>  
            <xsd:sequence>  
             <xsd:element name="Product"  
                          sql:relation="Product"   
                          sql:key-fields="ProductID"  
                          sql:relationship="OrderOD ODProduct">  
               <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
               </xsd:complexType>  
             </xsd:element>  
           </xsd:sequence>  
           <xsd:attribute name="OrderID"   type="xsd:integer" />   
           <xsd:attribute name="CustomerID"   type="xsd:string" />  
         </xsd:complexType>  
       </xsd:element>  
      </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="68abd-154">Das Schema gibt ein **\<Order>** Element mit einem untergeordneten **\<Product>** Element an.</span><span class="sxs-lookup"><span data-stu-id="68abd-154">The schema specifies an **\<Order>** element with a **\<Product>** child element.</span></span> <span data-ttu-id="68abd-155">Das **\<Order>** -Element wird der Ord-Tabelle zugeordnet, und das- **\<Product>** Element wird der Product-Tabelle in der-Datenbank zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="68abd-155">The **\<Order>** element maps to Ord table and the **\<Product>** element maps to the Product table in the database.</span></span> <span data-ttu-id="68abd-156">Die für das-Element angegebene Ketten Beziehung **\<Product>** identifiziert eine m:n-Beziehung, die durch die Order Detail-Tabelle dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="68abd-156">The chain relationship specified on the **\<Product>** element identifies a M:N relationship represented by the OrderDetail table.</span></span> <span data-ttu-id="68abd-157">(Eine Bestellung kann viele Produkte beinhalten, und ein Produkt kann in vielen Bestellungen enthalten sein.)</span><span class="sxs-lookup"><span data-stu-id="68abd-157">(An order can include many products, and a product can be included in many orders.)</span></span>  
  
 <span data-ttu-id="68abd-158">Wenn Sie mit diesem Schema einen Massenladevorgang für ein XML-Dokument durchführen, werden den Tabellen Ord, Product und OrderDetail Datensätze hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="68abd-158">When you are bulk loading an XML document with this schema, records are added to the Ord, Product, and OrderDetail tables.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="68abd-159">So testen Sie ein funktionstüchtiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="68abd-159">To test a working sample</span></span>  
  
1.  <span data-ttu-id="68abd-160">Erstellen Sie drei Tabellen:</span><span class="sxs-lookup"><span data-stu-id="68abd-160">Create three tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int  PRIMARY KEY,  
             CustomerID  varchar(5));  
    GO  
    CREATE TABLE Product (  
             ProductID   int PRIMARY KEY,  
             ProductName varchar(20));  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID));  
    GO  
    ```  
  
2.  <span data-ttu-id="68abd-161">Speichern Sie das oben in diesem Beispiel bereitgestellte Schema unter dem Dateinamen SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-161">Save the schema that is provided above in this example as SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="68abd-162">Speichern Sie die folgenden XML-Daten unter dem Dateinamen SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="68abd-162">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="1" CustomerID="ALFKI">  
        <Product ProductID="1" ProductName="Chai" />  
        <Product ProductID="2" ProductName="Chang" />  
      </Order>  
      <Order OrderID="2" CustomerID="ANATR">  
        <Product ProductID="3" ProductName="Aniseed Syrup" />  
        <Product ProductID="4" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="68abd-163">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="68abd-163">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="68abd-164">Fügen Sie zu dieser Datei den VBScript-Code hinzu, der am Anfang dieses Themas bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="68abd-164">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="68abd-165">Ändern Sie die Verbindungszeichenfolge, um den entsprechenden Server- und Datenbanknamen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="68abd-165">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="68abd-166">Entfernen Sie die Kommentierung der folgenden Zeilen aus dem Quellcode für dieses Beispiel.</span><span class="sxs-lookup"><span data-stu-id="68abd-166">Uncomment the following lines from the source code for this example.</span></span>  
  
    ```  
    objBL.CheckConstraints = True  
    objBL.Transaction=True  
    ```  
  
5.  <span data-ttu-id="68abd-167">Führen Sie den VBScript-Code aus.</span><span class="sxs-lookup"><span data-stu-id="68abd-167">Execute the VBScript code.</span></span> <span data-ttu-id="68abd-168">XML-Massenladen lädt das XML-Dokument in die Tabellen Ord und Product.</span><span class="sxs-lookup"><span data-stu-id="68abd-168">XML Bulk Load loads the XML document into the Ord and Product tables.</span></span>  
  
## <a name="d-bulk-loading-in-identity-type-columns"></a><span data-ttu-id="68abd-169">D:</span><span class="sxs-lookup"><span data-stu-id="68abd-169">D.</span></span> <span data-ttu-id="68abd-170">Massenladen in Identitätsspalten</span><span class="sxs-lookup"><span data-stu-id="68abd-170">Bulk loading in identity type columns</span></span>  
 <span data-ttu-id="68abd-171">Dieses Beispiel zeigt den Umgang mit Identitätsspalten beim Massenladen.</span><span class="sxs-lookup"><span data-stu-id="68abd-171">This example illustrates how bulk load handles identity type columns.</span></span> <span data-ttu-id="68abd-172">In dem Beispiel werden Daten in einem Massenvorgang in drei Tabellen (Ord, Product und OrderDetail) geladen.</span><span class="sxs-lookup"><span data-stu-id="68abd-172">In the example, data is bulk loaded into three tables (Ord, Product, and OrderDetail).</span></span>  
  
 <span data-ttu-id="68abd-173">Tabellen:</span><span class="sxs-lookup"><span data-stu-id="68abd-173">In these tables:</span></span>  
  
-   <span data-ttu-id="68abd-174">OrderID in der Ord-Tabelle ist eine Identitätsspalte.</span><span class="sxs-lookup"><span data-stu-id="68abd-174">OrderID in the Ord table is an identity type column</span></span>  
  
-   <span data-ttu-id="68abd-175">ProductID ist eine Identitätsspalte.</span><span class="sxs-lookup"><span data-stu-id="68abd-175">ProductID in the Product table is an identity type column.</span></span>  
  
-   <span data-ttu-id="68abd-176">Die Spalten OrderID und ProductID in der OrderDetail-Tabelle sind Fremdschlüsselspalten, die sich auf Primärschlüsselspalten in den Tabellen Ord und Product beziehen.</span><span class="sxs-lookup"><span data-stu-id="68abd-176">OrderID and ProductID columns in the OrderDetail are foreign key columns referring to corresponding primary key columns in the Ord and Product tables.</span></span>  
  
 <span data-ttu-id="68abd-177">Hier sehen Sie die Tabellenschemas für dieses Beispiel:</span><span class="sxs-lookup"><span data-stu-id="68abd-177">The following are the table schemas for this example:</span></span>  
  
```  
Ord (OrderID, CustomerID)  
Product (ProductID, ProductName)  
OrderDetail (OrderID, ProductID)  
```  
  
 <span data-ttu-id="68abd-178">In diesem Beispiel für XML-Massen laden ist die KeepIdentity-Eigenschaft des Bulkload-Objektmodells auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="68abd-178">In this example of XML Bulk Load, the KeepIdentity property of the BulkLoad object model is set to false.</span></span> <span data-ttu-id="68abd-179">Daher erstellt [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Identitätswerte für die Spalten ProductID und OrderID in den Tabellen Product und Ord (alle in den Dokumenten für das Massenladen angegebenen Werte werden ignoriert).</span><span class="sxs-lookup"><span data-stu-id="68abd-179">Therefore, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] generates identity values for the ProductID and OrderID columns in the Product and Ord tables, respectively (any values provided in the documents to be bulk loaded are ignored).</span></span>  
  
 <span data-ttu-id="68abd-180">In diesem Fall gibt der XML-Massenladevorgang die Primärschlüssel- bzw. Fremdschlüsselbeziehung zwischen Tabellen an.</span><span class="sxs-lookup"><span data-stu-id="68abd-180">In this case, XML Bulk Load identifies the primary key/foreign key relationship among tables.</span></span> <span data-ttu-id="68abd-181">Der Massenladevorgang fügt zunächst Datensätze in die Tabelle mit den Primärschlüsseln ein und gibt dann die von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] generierten Identitätswerte an die Tabellen mit den Fremdschlüsselspalten weiter.</span><span class="sxs-lookup"><span data-stu-id="68abd-181">Bulk Load first inserts records in the tables with the primary key, then propagates the identity value generated by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to the tables with foreign key columns.</span></span> <span data-ttu-id="68abd-182">Im folgenden Beispiel fügt der XML-Massenladevorgang Daten in dieser Reihenfolge in Tabellen ein:</span><span class="sxs-lookup"><span data-stu-id="68abd-182">In the following example, XML Bulk Load inserts data in tables in this order:</span></span>  
  
1.  <span data-ttu-id="68abd-183">Produkt</span><span class="sxs-lookup"><span data-stu-id="68abd-183">Product</span></span>  
  
2.  <span data-ttu-id="68abd-184">Ord</span><span class="sxs-lookup"><span data-stu-id="68abd-184">Ord</span></span>  
  
3.  <span data-ttu-id="68abd-185">OrderDetail</span><span class="sxs-lookup"><span data-stu-id="68abd-185">OrderDetail</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="68abd-186">Die Verarbeitungslogik erfordert, dass der XML-Massenladevorgang die Identitätswerte für das spätere Einfügen in die OrderDetails-Tabelle aufzeichnet, um sie in die Tabellen Products und Orders einzufügen.</span><span class="sxs-lookup"><span data-stu-id="68abd-186">In order to propagate identity values generated in the Products and Orders tables, the processing logic requires XML Bulk Load to keep track of these values for later insertion into the OrderDetails table.</span></span> <span data-ttu-id="68abd-187">Zu diesem Zweck erstellt der XML-Massenladevorgang Zwischentabellen, fügt die Daten in diese Tabellen ein und entfernt sie später.</span><span class="sxs-lookup"><span data-stu-id="68abd-187">To do that, XML Bulk Load creates intermediate tables, populates the data in these tables, and later removes them.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="68abd-188">So testen Sie ein funktionstüchtiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="68abd-188">To test a working sample</span></span>  
  
1.  <span data-ttu-id="68abd-189">Erstellen Sie die folgenden Tabellen:</span><span class="sxs-lookup"><span data-stu-id="68abd-189">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int identity(1,1)  PRIMARY KEY,  
             CustomerID  varchar(5));  
    GO  
    CREATE TABLE Product (  
             ProductID   int identity(1,1) PRIMARY KEY,  
             ProductName varchar(20));  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID));  
    GO  
    ```  
  
2.  <span data-ttu-id="68abd-190">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-190">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="68abd-191">Fügen Sie dieses XSD-Schema der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="68abd-191">Add this XSD schema to this file.</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
     <xsd:annotation>  
       <xsd:appinfo>  
        <sql:relationship name="OrderOD"  
              parent="Ord"  
              parent-key="OrderID"  
              child="OrderDetail"  
              child-key="OrderID" />  
        <sql:relationship name="ODProduct"  
              parent="OrderDetail"  
              parent-key="ProductID"  
              child="Product"  
              child-key="ProductID"   
              inverse="true"/>  
       </xsd:appinfo>  
     </xsd:annotation>  
  
      <xsd:element name="Order" sql:relation="Ord"   
                                sql:key-fields="OrderID" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="Product" sql:relation="Product"   
                         sql:key-fields="ProductID"  
                         sql:relationship="OrderOD ODProduct">  
              <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
              </xsd:complexType>  
            </xsd:element>  
         </xsd:sequence>  
            <xsd:attribute name="OrderID"   type="xsd:integer" />   
            <xsd:attribute name="CustomerID"   type="xsd:string" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="68abd-192">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-192">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="68abd-193">Fügen Sie das folgende XML-Dokument hinzu:</span><span class="sxs-lookup"><span data-stu-id="68abd-193">Add the following XML document.</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="11" CustomerID="ALFKI">  
        <Product ProductID="11" ProductName="Chai" />  
        <Product ProductID="22" ProductName="Chang" />  
      </Order>  
      <Order OrderID="22" CustomerID="ANATR">  
         <Product ProductID="33" ProductName="Aniseed Syrup" />  
        <Product ProductID="44" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="68abd-194">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="68abd-194">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="68abd-195">Fügen Sie dieser Datei den folgenden VBScript-Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="68abd-195">To this file, add the following VBScript code.</span></span> <span data-ttu-id="68abd-196">Ändern Sie die Verbindungszeichenfolge, um den entsprechenden Server- und Datenbanknamen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="68abd-196">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="68abd-197">Geben Sie den entsprechenden Pfad für die Dateien an, die als Parameter für die `Execute` Methode fungieren.</span><span class="sxs-lookup"><span data-stu-id="68abd-197">Specify the appropriate path for the files that serve as parameters to the `Execute` method.</span></span>  
  
    ```  
    Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "C:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Transaction = False  
    objBL.KeepIdentity = False  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    Set objBL = Nothing  
    MsgBox "Done."  
    ```  
  
5.  <span data-ttu-id="68abd-198">Führen Sie den VBScript-Code aus.</span><span class="sxs-lookup"><span data-stu-id="68abd-198">Execute the VBScript code.</span></span> <span data-ttu-id="68abd-199">Der XML-Massenladevorgang lädt die Daten in die entsprechenden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="68abd-199">The XML Bulk Load will load the data into the appropriate tables.</span></span>  
  
## <a name="e-generating-table-schemas-before-bulk-loading"></a><span data-ttu-id="68abd-200">E.</span><span class="sxs-lookup"><span data-stu-id="68abd-200">E.</span></span> <span data-ttu-id="68abd-201">Erstellen von Tabellenschemas vor dem Massenladen</span><span class="sxs-lookup"><span data-stu-id="68abd-201">Generating table schemas before bulk loading</span></span>  
 <span data-ttu-id="68abd-202">Der XML-Massenladevorgang kann die Tabellen optional erstellen, wenn sie vor dem Massenladen nicht vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="68abd-202">XML Bulk Load can optionally generate the tables if they do not exist before bulk loading.</span></span> <span data-ttu-id="68abd-203">Wenn Sie die SchemaGen-Eigenschaft des SQLXMLBulkLoad-Objekts auf "true" festlegen, wird dies durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="68abd-203">Setting the SchemaGen property of the SQLXMLBulkLoad object to TRUE does this.</span></span> <span data-ttu-id="68abd-204">Sie können optional auch XML-Massen laden anfordern, um vorhandene Tabellen zu löschen und neu zu erstellen, indem Sie die SGDropTables-Eigenschaft auf "true" festlegen.</span><span class="sxs-lookup"><span data-stu-id="68abd-204">You can also optionally request XML Bulk Load to drop any existing tables and re-create them by setting the SGDropTables property to TRUE.</span></span> <span data-ttu-id="68abd-205">Das folgende VBScript-Beispiel zeigt die Verwendung dieser Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="68abd-205">The following VBScript example illustrates the use of these properties.</span></span>  
  
 <span data-ttu-id="68abd-206">In diesem Beispiel werden außerdem zwei zusätzliche Eigenschaften auf TRUE festgelegt:</span><span class="sxs-lookup"><span data-stu-id="68abd-206">Also, this example sets two additional properties to TRUE:</span></span>  
  
-   <span data-ttu-id="68abd-207">CHECKCONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="68abd-207">CheckConstraints.</span></span> <span data-ttu-id="68abd-208">Durch Festlegen dieser Eigenschaft auf TRUE wird sichergestellt, dass das Einfügen von Daten in die Tabellen keine Einschränkungen verletzt, die für die Tabellen festgelegt wurden (in diesem Fall die Einschränkungen PRIMARY KEY bzw. FOREIGN KEY für die Tabellen Cust und CustOrder).</span><span class="sxs-lookup"><span data-stu-id="68abd-208">Setting this property to TRUE ensures that the data being inserted into the tables does not violate any constraints that have been specified on the tables (in this case the PRIMARY KEY/FOREIGN KEY constraints specified between the Cust and CustOrder tables).</span></span> <span data-ttu-id="68abd-209">Liegt eine Einschränkungsverletzung vor, schlägt das Massenladen fehl.</span><span class="sxs-lookup"><span data-stu-id="68abd-209">If there is a constraint violation, the bulk load fails.</span></span>  
  
-   <span data-ttu-id="68abd-210">XMLFragment.</span><span class="sxs-lookup"><span data-stu-id="68abd-210">XMLFragment.</span></span> <span data-ttu-id="68abd-211">Diese Eigenschaft muss auf TRUE festgelegt werden, da das XML-Beispieldokument (Datenquelle) kein einzelnes Element der obersten Ebene enthält (und daher ein Fragment ist).</span><span class="sxs-lookup"><span data-stu-id="68abd-211">This property must be set to TRUE because the sample XML document (data source) contains no single, top-level element (and is thus a fragment).</span></span>  
  
 <span data-ttu-id="68abd-212">Dies ist der VBScript-Code:</span><span class="sxs-lookup"><span data-stu-id="68abd-212">This is the VBScript code:</span></span>  
  
```  
Dim objBL   
Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
  
objBL.CheckConstraints=true  
objBL.XMLFragment = True  
objBL.SchemaGen = True  
objBL.SGDropTables = True  
  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
Set objBL = Nothing  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="68abd-213">So testen Sie ein funktionstüchtiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="68abd-213">To test a working sample</span></span>  
  
1.  <span data-ttu-id="68abd-214">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-214">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="68abd-215">Fügen Sie der Datei das XSD-Schema aus dem oben aufgeführten Beispiel "Verwenden von Kettenbeziehungen im Schema für das XML-Massenladen" hinzu.</span><span class="sxs-lookup"><span data-stu-id="68abd-215">Add the XSD schema that is provided in the earlier example, "Using chain relationships in the schema to bulk load XML", to the file.</span></span>  
  
2.  <span data-ttu-id="68abd-216">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-216">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="68abd-217">Fügen Sie der Datei das XML-Dokument aus dem oben aufgeführten Beispiel "Verwenden von Kettenbeziehungen im Schema für das XML-Massenladen" hinzu.</span><span class="sxs-lookup"><span data-stu-id="68abd-217">Add the XML document that is provided in the earlier example, "Using chain relationships in the schema to bulk load XML", to the file.</span></span> <span data-ttu-id="68abd-218">Entfernen Sie das- \<ROOT> Element aus dem Dokument (um es zu einem Fragment zu machen).</span><span class="sxs-lookup"><span data-stu-id="68abd-218">Remove the \<ROOT> element from the document (to make it a fragment).</span></span>  
  
3.  <span data-ttu-id="68abd-219">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="68abd-219">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="68abd-220">Fügen Sie dieser Datei den VBScript-Code in diesem Beispiel hinzu.</span><span class="sxs-lookup"><span data-stu-id="68abd-220">To this file, add the VBScript code in this example.</span></span> <span data-ttu-id="68abd-221">Ändern Sie die Verbindungszeichenfolge, um den entsprechenden Server- und Datenbanknamen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="68abd-221">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="68abd-222">Geben Sie den entsprechenden Pfad für die Dateien an, die als Parameter für die Execute-Methode angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="68abd-222">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
4.  <span data-ttu-id="68abd-223">Führen Sie den VBScript-Code aus.</span><span class="sxs-lookup"><span data-stu-id="68abd-223">Execute the VBScript code.</span></span> <span data-ttu-id="68abd-224">Der XML-Massenladevorgang erstellt die erforderlichen Tabellen basierend auf dem bereitgestellten Zuordnungsschema und lädt die Daten in einem Massenvorgang.</span><span class="sxs-lookup"><span data-stu-id="68abd-224">The XML Bulk Load creates the necessary tables on the basis of the mapping schema that is provided and bulk loads the data in it.</span></span>  
  
## <a name="f-bulk-loading-from-a-stream"></a><span data-ttu-id="68abd-225">F.</span><span class="sxs-lookup"><span data-stu-id="68abd-225">F.</span></span> <span data-ttu-id="68abd-226">Massenladen von einem Datenstrom</span><span class="sxs-lookup"><span data-stu-id="68abd-226">Bulk loading from a stream</span></span>  
 <span data-ttu-id="68abd-227">Die Execute-Methode des XML-Massen laden-Objektmodells nimmt zwei Parameter an.</span><span class="sxs-lookup"><span data-stu-id="68abd-227">The Execute method of the XML Bulk Load object model takes two parameters.</span></span> <span data-ttu-id="68abd-228">Der erste Parameter ist die Zuordnungsschemadatei.</span><span class="sxs-lookup"><span data-stu-id="68abd-228">The first parameter is the mapping schema file.</span></span> <span data-ttu-id="68abd-229">Der zweite Parameter gibt die XML-Daten an, die in die Datenbank geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="68abd-229">The second parameter provides the XML data that is to be loaded in the database.</span></span> <span data-ttu-id="68abd-230">Es gibt zwei Möglichkeiten, die XML-Daten an die Execute-Methode von XML-Massen laden zu übergeben:</span><span class="sxs-lookup"><span data-stu-id="68abd-230">There are two ways to pass the XML data to the Execute method of XML Bulk Load:</span></span>  
  
-   <span data-ttu-id="68abd-231">Angeben des Dateinamen als Parameter</span><span class="sxs-lookup"><span data-stu-id="68abd-231">Specify the file name as the parameter.</span></span>  
  
-   <span data-ttu-id="68abd-232">Übergeben eines Datenstroms, der die XML-Daten enthält</span><span class="sxs-lookup"><span data-stu-id="68abd-232">Pass a stream that contains the XML data.</span></span>  
  
 <span data-ttu-id="68abd-233">Dieses Beispiel zeigt, wie ein Datenstrom in einem Massenvorgang geladen wird.</span><span class="sxs-lookup"><span data-stu-id="68abd-233">This example illustrates how to bulk load from a stream.</span></span>  
  
 <span data-ttu-id="68abd-234">VBScript führt zunächst eine SELECT-Anweisung aus, um Kundeninformationen aus der Customers-Tabelle in der Northwind-Datenbank abzurufen.</span><span class="sxs-lookup"><span data-stu-id="68abd-234">VBScript first executes a SELECT statement to retrieve customer information from the Customers table in the Northwind database.</span></span> <span data-ttu-id="68abd-235">Da die FOR XML-Klausel (mit der ELEMENTS-Option) in der SELECT-Anweisung angegeben wurde, gibt die Abfrage ein elementzentriertes XML-Dokument in folgendem Format zurück:</span><span class="sxs-lookup"><span data-stu-id="68abd-235">Because the FOR XML clause is specified (with the ELEMENTS option) in the SELECT statement, the query returns an element-centric XML document of this form:</span></span>  
  
```  
<Customer>  
  <CustomerID>..</CustomerID>  
  <CompanyName>..</CompanyName>  
  <City>..</City>  
</Customer>  
...  
```  
  
 <span data-ttu-id="68abd-236">Das Skript übergibt dann den XML-Code als Datenstrom an die Execute-Methode als zweiten Parameter.</span><span class="sxs-lookup"><span data-stu-id="68abd-236">The script then passes the XML as a stream to the Execute method as its second parameter.</span></span> <span data-ttu-id="68abd-237">Mit der Execute-Methode werden die Daten per Massen Vorgang in die Cust-Tabelle geladen.</span><span class="sxs-lookup"><span data-stu-id="68abd-237">The Execute method bulk loads the data into the Cust table.</span></span>  
  
 <span data-ttu-id="68abd-238">Da mit diesem Skript die SchemaGen-Eigenschaft auf true und die SGDropTables-Eigenschaft auf true festgelegt wird, erstellt das XML-Massen laden die Cust-Tabelle in der angegebenen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="68abd-238">Because this script sets the SchemaGen property to TRUE and SGDropTables property to TRUE, XML Bulk Load creates the Cust table in the specified database.</span></span> <span data-ttu-id="68abd-239">(Wenn die Tabelle bereits vorhanden ist, löscht sie zuerst die Tabelle und erstellt sie dann erneut.)</span><span class="sxs-lookup"><span data-stu-id="68abd-239">(If the table already exists, it first drops the table and then re-creates it.)</span></span>  
  
 <span data-ttu-id="68abd-240">Dies ist das VB-Script-Beispiel:</span><span class="sxs-lookup"><span data-stu-id="68abd-240">This is the VBScript example:</span></span>  
  
```  
Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
Set objCmd = CreateObject("ADODB.Command")  
Set objConn = CreateObject("ADODB.Connection")  
Set objStrmOut = CreateObject ("ADODB.Stream")  
  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile     = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.SchemaGen        = True  
objBL.SGDropTables     = True  
objBL.XMLFragment      = True  
' Open a connection to the instance of SQL Server to get the source data.  
  
objConn.Open "provider=SQLOLEDB;server=(local);database=tempdb;integrated security=SSPI"  
Set objCmd.ActiveConnection = objConn  
objCmd.CommandText = "SELECT CustomerID, CompanyName, City FROM Customers FOR XML AUTO, ELEMENTS"  
  
' Open the return stream and execute the command.  
Const adCRLF = -1  
Const adExecuteStream = 1024  
objStrmOut.Open  
objStrmOut.LineSeparator = adCRLF  
objCmd.Properties("Output Stream").Value = objStrmOut  
objCmd.Execute , , adExecuteStream  
objStrmOut.Position = 0  
  
' Execute bulk load. Read source XML data from the stream.  
objBL.Execute "SampleSchema.xml", objStrmOut  
  
Set objBL = Nothing  
```  
  
 <span data-ttu-id="68abd-241">Das folgende XSD-Zuordnungsschema stellt die notwendigen Informationen bereit, um die Tabelle zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="68abd-241">The following XSD mapping schema provides the necessary information to create the table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:element name="ROOT" sql:is-constant="true" >  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element ref="Customers"/>  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="Customers" sql:relation="Cust" >  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element name="CustomerID"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(5)"/>  
      <xsd:element name="CompanyName"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(40)"/>  
      <xsd:element name="City"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(40)"/>  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="68abd-242">Dies ist das entsprechende XDR-Schema:</span><span class="sxs-lookup"><span data-stu-id="68abd-242">This is equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
    </ElementType>  
</Schema>  
```  
  
### <a name="opening-a-stream-on-an-existing-file"></a><span data-ttu-id="68abd-243">Öffnen eines Datenstroms in einer vorhandenen Datei</span><span class="sxs-lookup"><span data-stu-id="68abd-243">Opening a Stream on an Existing File</span></span>  
 <span data-ttu-id="68abd-244">Sie können auch einen Stream für eine vorhandene XML-Datendatei öffnen und den Datenstrom als Parameter an die Execute-Methode übergeben (anstatt den Dateinamen als Parameter zu übergeben).</span><span class="sxs-lookup"><span data-stu-id="68abd-244">You can also open a stream on an existing XML data file and pass the stream as a parameter to the Execute method (instead of passing the file name as the parameter).</span></span>  
  
 <span data-ttu-id="68abd-245">In diesem Visual Basic-Beispiel wird ein Datenstrom als Parameter übergeben:</span><span class="sxs-lookup"><span data-stu-id="68abd-245">This is a Visual Basic example of passing a stream as the parameter:</span></span>  
  
```  
Private Sub Form_Load()  
Dim objBL As New SQLXMLBulkLoad  
Dim objStrm As New ADODB.Stream  
Dim objFileSystem As New Scripting.FileSystemObject  
Dim objFile As Scripting.TextStream  
  
MsgBox "Begin BulkLoad..."  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.SchemaGen = True  
objBL.SGDropTables = True  
' Here again a stream is specified that contains the source data   
' (instead of the file name). But this is just an illustration.  
' Usually this is useful if you have an XML data   
' stream that is created by some other means that you want to bulk   
' load. This example starts with an XML text file, so it may not be the   
' best to use a stream (you can specify the file name directly).  
' Here you could have specified the file name itself.   
Set objFile = objFileSystem.OpenTextFile("c:\SampleData.xml")  
objStrm.Open  
objStrm.WriteText objFile.ReadAll  
objStrm.Position = 0  
objBL.Execute "c:\SampleSchema.xml", objStrm  
  
Set objBL = Nothing  
MsgBox "Done."  
End Sub  
```  
  
 <span data-ttu-id="68abd-246">Zum Testen der Anwendung verwenden Sie das folgende XML-Dokument in einer Datei (SampleData.xml) sowie das in diesem Beispiel angegebene XSD-Schema:</span><span class="sxs-lookup"><span data-stu-id="68abd-246">To test the application, use the following XML document in a file (SampleData.xml) and the XSD schema that is provided in this example:</span></span>  
  
 <span data-ttu-id="68abd-247">Dies sind die XML-Quelldaten (SampleData.xml):</span><span class="sxs-lookup"><span data-stu-id="68abd-247">This is the XML source data (SampleData.xml):</span></span>  
  
```  
<ROOT>  
  <Customers>  
    <CustomerID>1111</CustomerID>  
    <CompanyName>Hanari Carnes</CompanyName>  
    <City>NY</City>  
    <Order OrderID="1" />  
    <Order OrderID="2" />  
  </Customers>  
  
  <Customers>  
    <CustomerID>1112</CustomerID>  
    <CompanyName>Toms Spezialitten</CompanyName>  
     <City>LA</City>  
    <Order OrderID="3" />  
  </Customers>  
  <Customers>  
    <CustomerID>1113</CustomerID>  
    <CompanyName>Victuailles en stock</CompanyName>  
    <Order CustomerID= "4444" OrderID="4" />  
</Customers>  
</ROOT>  
```  
  
 <span data-ttu-id="68abd-248">Dies ist das entsprechende XDR-Schema:</span><span class="sxs-lookup"><span data-stu-id="68abd-248">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
             <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
</Schema>  
```  
  
## <a name="g-bulk-loading-in-overflow-columns"></a><span data-ttu-id="68abd-249">G.</span><span class="sxs-lookup"><span data-stu-id="68abd-249">G.</span></span> <span data-ttu-id="68abd-250">Massenladen in Überlaufspalten</span><span class="sxs-lookup"><span data-stu-id="68abd-250">Bulk loading in overflow columns</span></span>  
 <span data-ttu-id="68abd-251">Wenn im Zuordnungsschema mit der `sql:overflow-field`-Anmerkung eine Überlaufspalte festgelegt wurde, kopiert der XML-Massenladevorgang alle nicht verwendeten Daten aus dem Quelldokument in diese Spalte.</span><span class="sxs-lookup"><span data-stu-id="68abd-251">If the mapping schema specifies an overflow column by using the `sql:overflow-field` annotation, XML Bulk Load copies all unconsumed data from the source document into this column.</span></span>  
  
 <span data-ttu-id="68abd-252">Beachten Sie dieses XSD-Schema:</span><span class="sxs-lookup"><span data-stu-id="68abd-252">Consider this XSD schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
          parent="Cust"  
          parent-key="CustomerID"  
          child="CustOrder"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  <xsd:element name="Customers" sql:relation="Cust"  
                                sql:overflow-field="OverflowColumn" >  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="CustomerID"  type="xsd:integer" />  
       <xsd:element name="CompanyName" type="xsd:string" />  
       <xsd:element name="City"        type="xsd:string" />  
       <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
         <xsd:complexType>  
          <xsd:attribute name="OrderID" type="xsd:integer" />  
          <xsd:attribute name="CustomerID" type="xsd:integer" />  
         </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="68abd-253">Das Schema identifiziert eine Überlaufspalte (OverflowColumn) für die Cust-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="68abd-253">The schema identifies an overflow column (OverflowColumn) for the Cust table.</span></span> <span data-ttu-id="68abd-254">Folglich werden dieser Spalte alle nicht verbrauchten XML-Daten für jedes **\<Customer>** Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="68abd-254">As a result, all unconsumed XML data for each **\<Customer>** element is added to this column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68abd-255">Alle abstrakten Elemente (Elemente, für die **abstract = "true"** angegeben ist) und alle unzulässigen Attribute (Attribute, für die **"unzulässig =" true "** angegeben ist) gelten als Überlauf beim XML-Massen laden und werden ggf. der Überlauf Spalte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="68abd-255">All abstract elements (elements for which **abstract="true"** is specified) and all prohibited attributes (attributes for which **prohibited="true"** is specified) are considered overflow by XML Bulk Load and are added to the overflow column, if specified.</span></span> <span data-ttu-id="68abd-256">(Andernfalls werden sie ignoriert.)</span><span class="sxs-lookup"><span data-stu-id="68abd-256">(Otherwise, they are ignored.)</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="68abd-257">So testen Sie ein funktionstüchtiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="68abd-257">To test a working sample</span></span>  
  
1.  <span data-ttu-id="68abd-258">Erstellen Sie zwei Tabellen in der **tempdb** -Datenbank:</span><span class="sxs-lookup"><span data-stu-id="68abd-258">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust (  
                  CustomerID     int         PRIMARY KEY,  
                  CompanyName    varchar(20) NOT NULL,  
                  City           varchar(20) DEFAULT 'Seattle',  
                  OverflowColumn nvarchar(200));  
    GO  
    CREATE TABLE CustOrder (  
                  OrderID    int PRIMARY KEY,  
                  CustomerID int FOREIGN KEY   
                                 REFERENCES Cust(CustomerID));  
    GO  
    ```  
  
2.  <span data-ttu-id="68abd-259">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-259">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="68abd-260">Fügen Sie der Datei das XSD-Schema hinzu, das in diesem Beispiel bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="68abd-260">Add the XSD schema that is provided in this example to the file.</span></span>  
  
3.  <span data-ttu-id="68abd-261">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-261">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="68abd-262">Fügen Sie der Datei das folgende XML-Dokument hinzu:</span><span class="sxs-lookup"><span data-stu-id="68abd-262">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City><![CDATA[NY]]> </City>  
        <Junk>garbage in overflow</Junk>  
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
         <![CDATA[LA]]>   
        <!-- <xyz><address>111 Maple, Seattle</address></xyz>   -->  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="68abd-263">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="68abd-263">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="68abd-264">Fügen Sie dieser Datei den folgenden VBScript-Code (Microsoft Visual Basic Scripting Edition) hinzu.</span><span class="sxs-lookup"><span data-stu-id="68abd-264">To this file, add the following Microsoft Visual Basic Scripting Edition (VBScript) code.</span></span> <span data-ttu-id="68abd-265">Ändern Sie die Verbindungszeichenfolge, um den entsprechenden Server- und Datenbanknamen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="68abd-265">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="68abd-266">Geben Sie den entsprechenden Pfad für die Dateien an, die als Parameter für die Execute-Methode angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="68abd-266">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="68abd-267">Führen Sie den VBScript-Code aus.</span><span class="sxs-lookup"><span data-stu-id="68abd-267">Execute the VBScript code.</span></span>  
  
 <span data-ttu-id="68abd-268">Dies ist das entsprechende XDR-Schema:</span><span class="sxs-lookup"><span data-stu-id="68abd-268">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"   
                       sql:overflow-field="OverflowColumn"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
             <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
</Schema>  
```  
  
## <a name="h-specifying-the-file-path-for-temp-files-in-transaction-mode"></a><span data-ttu-id="68abd-269">H.</span><span class="sxs-lookup"><span data-stu-id="68abd-269">H.</span></span> <span data-ttu-id="68abd-270">Angeben des Dateipfads für temporäre Dateien im Transaktionsmodus</span><span class="sxs-lookup"><span data-stu-id="68abd-270">Specifying the file path for temp files in transaction mode</span></span>  
 <span data-ttu-id="68abd-271">Wenn Sie ein Massen laden im Transaktionsmodus ausführen (d. h., wenn die Transaction-Eigenschaft auf true festgelegt ist), müssen Sie auch die TempFilePath-Eigenschaft festlegen, wenn eine der folgenden Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="68abd-271">When you are bulk loading in transaction mode (that is, when the Transaction property is set to TRUE), you also must set the TempFilePath property when either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="68abd-272">Sie führen einen Massenladevorgang zu einem Remoteserver aus.</span><span class="sxs-lookup"><span data-stu-id="68abd-272">You are bulk loading to a remote server.</span></span>  
  
-   <span data-ttu-id="68abd-273">Sie möchten zum Speichern der Dateien, die im Transaktionsmodus erstellt werden, ein alternatives lokales Laufwerk oder einen alternativen Ordner verwenden (einen anderen als von der TEMP-Umgebungsvariable festgelegten Pfad).</span><span class="sxs-lookup"><span data-stu-id="68abd-273">You want to use an alternate local drive or folder (one other than the path that is specified by the TEMP environment variable) to store the temporary files that are created in the transaction mode.</span></span>  
  
 <span data-ttu-id="68abd-274">Der folgende VBScript-Code lädt beispielsweise im Transaktionsmodus Daten in einem Massenvorgang von der Datei SampleXMLData.xml in die Datenbanktabellen.</span><span class="sxs-lookup"><span data-stu-id="68abd-274">For example, the following VBScript code bulk loads data from the SampleXMLData.xml file into the database tables in transaction mode.</span></span> <span data-ttu-id="68abd-275">Die TempFilePath-Eigenschaft wird angegeben, um den Pfad für die temporären Dateien festzulegen, die im Transaktionsmodus generiert werden.</span><span class="sxs-lookup"><span data-stu-id="68abd-275">The TempFilePath property is specified to set the path for the temporary files that are generated in transaction mode.</span></span>  
  
```  
set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.Transaction=True  
objBL.TempFilePath="\\Server\MyDir"  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
set objBL=Nothing  
```  
  
> [!NOTE]  
>  <span data-ttu-id="68abd-276">Der Pfad für die temporäre Datei muss ein freigegebener Speicherort sein, auf den das Dienstkonto der Zielinstanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] und das Konto, das die Massenladeanwendung ausführt, zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="68abd-276">The temporary file path must be a shared location that is accessible to the service account of the target instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and to the account that is running the bulk load application.</span></span> <span data-ttu-id="68abd-277">Der temporäre Dateipfad muss ein UNC-Pfad sein (z \\ . b. \servername\sharename), es sei denn, Sie erstellen einen Massen Ladevorgang auf einem lokalen Server.</span><span class="sxs-lookup"><span data-stu-id="68abd-277">Unless you are bulk loading on a local server, the temporary file path must be a UNC path (such as \\\servername\sharename).</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="68abd-278">So testen Sie ein funktionstüchtiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="68abd-278">To test a working sample</span></span>  
  
1.  <span data-ttu-id="68abd-279">Erstellen Sie diese Tabelle in der **tempdb** -Datenbank:</span><span class="sxs-lookup"><span data-stu-id="68abd-279">Create this table in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust (     CustomerID uniqueidentifier,   
          LastName  varchar(20));  
    GO  
    ```  
  
2.  <span data-ttu-id="68abd-280">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-280">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="68abd-281">Fügen Sie das folgende XSD-Schema der Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="68abd-281">Add the following XSD schema to the file:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:attribute name="CustomerID"  type="xsd:string" />  
         <xsd:attribute name="LastName" type="xsd:string" />  
       </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="68abd-282">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-282">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="68abd-283">Fügen Sie der Datei das folgende XML-Dokument hinzu:</span><span class="sxs-lookup"><span data-stu-id="68abd-283">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
    <Customers CustomerID="6F9619FF-8B86-D011-B42D-00C04FC964FF"   
               LastName="Smith" />  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="68abd-284">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="68abd-284">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="68abd-285">Fügen Sie dieser Datei den folgenden VBScript-Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="68abd-285">To this file, add the following VBScript code.</span></span> <span data-ttu-id="68abd-286">Ändern Sie die Verbindungszeichenfolge, um den entsprechenden Server- und Datenbanknamen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="68abd-286">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="68abd-287">Geben Sie den entsprechenden Pfad für die Dateien an, die als Parameter für die Execute-Methode angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="68abd-287">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span> <span data-ttu-id="68abd-288">Geben Sie auch den entsprechenden Pfad für die TempFilePath-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="68abd-288">Also specify the appropriate path for the TempFilePath property.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Transaction=True  
    objBL.TempFilePath="\\server\folder"  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="68abd-289">Führen Sie den VBScript-Code aus.</span><span class="sxs-lookup"><span data-stu-id="68abd-289">Execute the VBScript code.</span></span>  
  
     <span data-ttu-id="68abd-290">Das Schema muss die entsprechende `sql:datatype` für das **CustomerID-** Attribut angeben, wenn der Wert für **CustomerID** als GUID angegeben ist, die geschweifte Klammern ({und}) enthält, z. b.:</span><span class="sxs-lookup"><span data-stu-id="68abd-290">The schema must specify the corresponding `sql:datatype` for the **CustomerID** attribute when the value for **CustomerID** is specified as a GUID that includes braces ({ and }), such as:</span></span>  
  
    ```  
    <ROOT>  
    <Customers CustomerID="{6F9619FF-8B86-D011-B42D-00C04FC964FF}"   
               LastName="Smith" />  
    </ROOT>  
    ```  
  
     <span data-ttu-id="68abd-291">Dies ist das aktualisierte Schema:</span><span class="sxs-lookup"><span data-stu-id="68abd-291">This is the updated schema:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:attribute name="CustomerID"  type="xsd:string"   
                        sql:datatype="uniqueidentifier" />  
         <xsd:attribute name="LastName" type="xsd:string" />  
       </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
     <span data-ttu-id="68abd-292">Wenn `sql:datatype` angegeben wird, das den Spaltentyp als identifiziert `uniqueidentifier` , werden durch den Massen Ladevorgang die geschweiften Klammern ({und}) aus dem **CustomerID-** Wert entfernt, bevor Sie in die Spalte eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="68abd-292">When `sql:datatype` is specified identifying the column type as `uniqueidentifier`, the bulk load operation removes the braces ({ and }) from the **CustomerID** value before inserting it in the column.</span></span>  
  
 <span data-ttu-id="68abd-293">Dies ist das entsprechende XDR-Schema:</span><span class="sxs-lookup"><span data-stu-id="68abd-293">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
<ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
</ElementType>  
<ElementType name="Customers" sql:relation="Cust" >  
  <AttributeType name="CustomerID"  sql:datatype="uniqueidentifier" />  
  <AttributeType name="LastName"   />  
  
  <attribute type="CustomerID" />  
  <attribute type="LastName"   />  
</ElementType>  
</Schema>  
```  
  
## <a name="i-using-an-existing-database-connection-with-the-connectioncommand-property"></a><span data-ttu-id="68abd-294">I.</span><span class="sxs-lookup"><span data-stu-id="68abd-294">I.</span></span> <span data-ttu-id="68abd-295">Verwenden einer vorhandenen Datenbankverbindung mit der "ConnectionCommand"-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="68abd-295">Using an existing database connection with the ConnectionCommand property</span></span>  
 <span data-ttu-id="68abd-296">Sie können eine vorhandene ADO-Verbindung für das XML-Massenladen verwenden.</span><span class="sxs-lookup"><span data-stu-id="68abd-296">You can use an existing ADO connection to bulk load XML.</span></span> <span data-ttu-id="68abd-297">Dies ist dann hilfreich, wenn der XML-Massenladevorgang nur einer von mehreren Vorgängen ist, der für eine Datenquelle ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="68abd-297">This is useful if XML Bulk Load is just one of many operations that will be performed on a data source.</span></span>  
  
 <span data-ttu-id="68abd-298">Die ConnectionCommand-Eigenschaft ermöglicht Ihnen, eine vorhandene ADO-Verbindung mithilfe eines ADO-Befehls Objekts zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="68abd-298">The ConnectionCommand property enables you to use an existing ADO connection by using an ADO command object.</span></span> <span data-ttu-id="68abd-299">Dies wird im folgenden Visual Basic-Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="68abd-299">This is illustrated in the following Visual Basic example:</span></span>  
  
```  
Private Sub Form_Load()  
Dim objBL As New SQLXMLBulkLoad4  
Dim objCmd As New ADODB.Command  
Dim objConn As New ADODB.Connection  
  
'Open a connection to an instance of SQL Server.  
objConn.Open "provider=SQLOLEDB;data source=(local);database=tempdb;integrated security=SSPI"  
'Ask the Command object to use the connection just established.  
Set objCmd.ActiveConnection = objConn  
  
'Tell Bulk Load to use the active command object that is using the Connection obj.  
objBL.ConnectionCommand = objCmd  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
'The Transaction property must be set to True if you use ConnectionCommand.  
objBL.Transaction = True  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
Set objBL = Nothing  
End Sub  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="68abd-300">So testen Sie ein funktionstüchtiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="68abd-300">To test a working sample</span></span>  
  
1.  <span data-ttu-id="68abd-301">Erstellen Sie zwei Tabellen in der **tempdb** -Datenbank:</span><span class="sxs-lookup"><span data-stu-id="68abd-301">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust(  
                   CustomerID   varchar(5) PRIMARY KEY,  
                   CompanyName  varchar(30),  
                   City         varchar(20));  
    GO  
    CREATE TABLE CustOrder(  
                   CustomerID  varchar(5) references Cust (CustomerID),  
                   OrderID     varchar(5) PRIMARY KEY);  
    GO  
    ```  
  
2.  <span data-ttu-id="68abd-302">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-302">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="68abd-303">Fügen Sie das folgende XSD-Schema der Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="68abd-303">Add the following XSD schema to the file:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
    <xsd:annotation>  
      <xsd:appinfo>  
        <sql:relationship name="CustCustOrder"  
              parent="Cust"  
              parent-key="CustomerID"  
              child="CustOrder"  
              child-key="CustomerID" />  
      </xsd:appinfo>  
    </xsd:annotation>  
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:sequence>  
           <xsd:element name="CustomerID"  type="xsd:integer" />  
           <xsd:element name="CompanyName" type="xsd:string" />  
           <xsd:element name="City"        type="xsd:string" />  
           <xsd:element name="Order"   
                              sql:relation="CustOrder"  
                              sql:relationship="CustCustOrder" >  
             <xsd:complexType>  
              <xsd:attribute name="OrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:integer" />  
             </xsd:complexType>  
           </xsd:element>  
         </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="68abd-304">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-304">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="68abd-305">Fügen Sie der Datei das folgende XML-Dokument hinzu:</span><span class="sxs-lookup"><span data-stu-id="68abd-305">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City>NY</City>  
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
         <City>LA</City>  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="68abd-306">Erstellen Sie eine Visual Basic (Standard-EXE)-Anwendung und den vorangehenden Code.</span><span class="sxs-lookup"><span data-stu-id="68abd-306">Create a Visual Basic (Standard EXE) application and the preceding code.</span></span> <span data-ttu-id="68abd-307">Fügen Sie dem Projekt die folgenden Verweise hinzu:</span><span class="sxs-lookup"><span data-stu-id="68abd-307">Add these references to the project:</span></span>  
  
    ```  
    Microsoft XML BulkLoad for SQL Server 4.0 Type Library  
    Microsoft ActiveX Data objects 2.6 Library  
    ```  
  
5.  <span data-ttu-id="68abd-308">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="68abd-308">Execute the application.</span></span>  
  
 <span data-ttu-id="68abd-309">Dies ist das entsprechende XDR-Schema:</span><span class="sxs-lookup"><span data-stu-id="68abd-309">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
         <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
</Schema>  
```  
  
## <a name="j-bulk-loading-in-xml-data-type-columns"></a><span data-ttu-id="68abd-310">J.</span><span class="sxs-lookup"><span data-stu-id="68abd-310">J.</span></span> <span data-ttu-id="68abd-311">Massenladen in XML-Datentypspalten</span><span class="sxs-lookup"><span data-stu-id="68abd-311">Bulk loading in xml Data Type columns</span></span>  
 <span data-ttu-id="68abd-312">Wenn das Zuordnungschema eine [XML-Datentyp](/sql/t-sql/xml/xml-transact-sql) Spalte mithilfe der-Anmerkung angibt `sql:datatype="xml"` , kann XML-Massen laden XML-untergeordnete Elemente für das zugeordnete Feld aus dem Quelldokument in diese Spalte kopieren.</span><span class="sxs-lookup"><span data-stu-id="68abd-312">If the mapping schema specifies a [xml data type](/sql/t-sql/xml/xml-transact-sql) column by using the `sql:datatype="xml"` annotation, XML Bulk Load can copy XML child elements for the mapped field from the source document into this column.</span></span>  
  
 <span data-ttu-id="68abd-313">Beachten Sie das folgende XSD-Schema, das eine Sicht der Production.ProductModel-Tabelle in der AdventureWorks-Beispieldatenbank zuordnet.</span><span class="sxs-lookup"><span data-stu-id="68abd-313">Consider the following XSD schema, which maps a view of the Production.ProductModel table in the AdventureWorks sample database.</span></span> <span data-ttu-id="68abd-314">In dieser Tabelle wird das CatalogDescription-Feld des `xml` -Datentyps **\<Desc>** mithilfe der Anmerkungen `sql:field` und einem-Element zugeordnet `sql:datatype="xml"` .</span><span class="sxs-lookup"><span data-stu-id="68abd-314">In this table, the CatalogDescription field of `xml` data type is mapped to a **\<Desc>** element using the `sql:field` and `sql:datatype="xml"` annotations.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
           xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
           xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">   
  <xsd:element name="ProductModel"  sql:relation="Production.ProductModel" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Name" type="xs:string"></xsd:element>  
        <xsd:element name="Desc" sql:field="CatalogDescription" sql:datatype="xml">  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element name="ProductDescription">  
              <xsd:complexType>  
                <xsd:sequence>  
                  <xsd:element name="Summary" type="xs:anyType"/>  
                </xsd:sequence>  
              </xsd:complexType>  
            </xsd:element>  
          </xsd:sequence>  
        </xsd:complexType>  
        </xsd:element>   
     </xsd:sequence>  
     <xsd:attribute name="ProductModelID" sql:field="ProductModelID" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="68abd-315">So testen Sie ein funktionstüchtiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="68abd-315">To test a working sample</span></span>  
  
1.  <span data-ttu-id="68abd-316">Prüfen Sie, ob die AdventureWorks-Beispieldatenbank installiert ist.</span><span class="sxs-lookup"><span data-stu-id="68abd-316">Verify that the AdventureWorks sample database is installed.</span></span>  
  
2.  <span data-ttu-id="68abd-317">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-317">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="68abd-318">Kopieren Sie das oben stehende XSD-Schema, fügen Sie es in die Datei ein, und speichern Sie diese.</span><span class="sxs-lookup"><span data-stu-id="68abd-318">Copy the XSD schema above and paste it into the file and save it.</span></span>  
  
3.  <span data-ttu-id="68abd-319">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="68abd-319">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="68abd-320">Kopieren Sie das folgende XML-Dokument, fügen Sie es in die Datei ein und speichern diese in dem selben Ordner, den Sie im vorherigen Schritt verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="68abd-320">Copy the following XML document below and paste it into the file and save it in the same folder as was used for the previous step.</span></span>  
  
    ```  
    <ProductModel ProductModelID="2005">  
        <Name>Mountain-100 (2005 model)</Name>  
        <Desc><?xml-stylesheet href="ProductDescription.xsl" type="text/xsl"?>  
            <p1:ProductDescription xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription"   
                  xmlns:wm="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"   
                  xmlns:wf="http://www.adventure-works.com/schemas/OtherFeatures"   
                  xmlns:html="http://www.w3.org/1999/xhtml"   
                  xmlns="">  
                <p1:Summary>  
                    <html:p>Our top-of-the-line competition mountain bike.   
          Performance-enhancing options include the innovative HL Frame,   
          super-smooth front suspension, and traction for all terrain.  
                            </html:p>  
                </p1:Summary>  
                <p1:Manufacturer>  
                    <p1:Name>AdventureWorks</p1:Name>  
                    <p1:Copyright>2002-2005</p1:Copyright>  
                    <p1:ProductURL>HTTP://www.Adventure-works.com</p1:ProductURL>  
                </p1:Manufacturer>  
                <p1:Features>These are the product highlights.   
                     <wm:Warranty>  
                        <wm:WarrantyPeriod>3 years</wm:WarrantyPeriod>  
                        <wm:Description>parts and labor</wm:Description>  
                    </wm:Warranty><wm:Maintenance>  
                        <wm:NoOfYears>10 years</wm:NoOfYears>  
                        <wm:Description>maintenance contract available through your dealer or any AdventureWorks retail store.</wm:Description>  
                    </wm:Maintenance><wf:wheel>High performance wheels.</wf:wheel><wf:saddle>  
                        <html:i>Anatomic design</html:i> and made from durable leather for a full-day of riding in comfort.</wf:saddle><wf:pedal>  
                        <html:b>Top-of-the-line</html:b> clipless pedals with adjustable tension.</wf:pedal><wf:BikeFrame>Each frame is hand-crafted in our Bothell facility to the optimum diameter   
          and wall-thickness required of a premium mountain frame.   
          The heat-treated welded aluminum frame has a larger diameter tube that absorbs the bumps.</wf:BikeFrame><wf:crankset> Triple crankset; alumunim crank arm; flawless shifting. </wf:crankset></p1:Features>  
                <!-- add one or more of these elements... one for each specific product in this product model -->  
                <p1:Picture>  
                    <p1:Angle>front</p1:Angle>  
                    <p1:Size>small</p1:Size>  
                    <p1:ProductPhotoID>118</p1:ProductPhotoID>  
                </p1:Picture>  
                <!-- add any tags in <specifications> -->  
                <p1:Specifications> These are the product specifications.  
                       <Material>Almuminum Alloy</Material><Color>Available in most colors</Color><ProductLine>Mountain bike</ProductLine><Style>Unisex</Style><RiderExperience>Advanced to Professional riders</RiderExperience></p1:Specifications>  
            </p1:ProductDescription>  
        </Desc>  
    </ProductModel>  
    ```  
  
4.  <span data-ttu-id="68abd-321">Erstellen Sie eine Datei in Ihrem bevorzugten Text- oder XML-Editor, und speichern Sie sie als BulkloadXml.vbs.</span><span class="sxs-lookup"><span data-stu-id="68abd-321">Create a file in your preferred text or XML editor, and save it as BulkloadXml.vbs.</span></span> <span data-ttu-id="68abd-322">Kopieren Sie den folgenden VBScript-Code, und fügen Sie ihn in die Datei ein.</span><span class="sxs-lookup"><span data-stu-id="68abd-322">Copy the following VBScript code and paste it into the file.</span></span> <span data-ttu-id="68abd-323">Speichern Sie die Datei in dem gleichen Ordner wie die vorherigen XML-Daten- und Schemadateien.</span><span class="sxs-lookup"><span data-stu-id="68abd-323">Save it in the same folder as was used for the previous XML data and schema files.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=MyServer;database=AdventureWorks;integrated security=SSPI"  
  
    Dim fso, sAppPath  
    Set fso = CreateObject("Scripting.FileSystemObject")   
    sAppPath = fso.GetFolder(".")   
  
    objBL.ErrorLogFile = sAppPath & "\error.log"  
  
    'Execute XML bulkload using file.  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="68abd-324">Führen Sie das Skript BulkloadXml.vbs aus.</span><span class="sxs-lookup"><span data-stu-id="68abd-324">Execute the BulkloadXml.vbs script.</span></span>  
  
  
