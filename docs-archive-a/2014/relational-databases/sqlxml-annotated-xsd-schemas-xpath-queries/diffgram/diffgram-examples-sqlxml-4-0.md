---
title: DiffGram-Beispiele (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], examples
- examples [SQLXML], DiffGram
- diffgr:parentID
- parentID annotation
ms.assetid: fc148583-dfd3-4efb-a413-f47b150b0975
author: rothja
ms.author: jroth
ms.openlocfilehash: 04fb355af01f9853149a84af72471375d9135468
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618600"
---
# <a name="diffgram-examples-sqlxml-40"></a><span data-ttu-id="ffd35-102">DiffGram-Beispiele (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ffd35-102">DiffGram Examples (SQLXML 4.0)</span></span>
  <span data-ttu-id="ffd35-103">Die Beispiele in diesem Thema umfassen DiffGrams, mit denen Einfüge-, Update- und Löschvorgänge in der Datenbank vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="ffd35-103">The examples in this topic consist of DiffGrams that perform insert, update, and delete operations to the database.</span></span> <span data-ttu-id="ffd35-104">Bevor Sie die Beispiele verwenden, beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ffd35-104">Before using the examples, note the following:</span></span>  
  
-   <span data-ttu-id="ffd35-105">In den Beispielen werden zwei Tabellen verwendet (Cust und Ord), die erstellt werden müssen, wenn Sie die DiffGram-Beispiele testen möchten:</span><span class="sxs-lookup"><span data-stu-id="ffd35-105">The examples use two tables (Cust and Ord) that must be created if you want to test the DiffGram examples:</span></span>  
  
    ```  
    Cust(CustomerID, CompanyName, ContactName)  
    Ord(OrderID, CustomerID)  
    ```  
  
-   <span data-ttu-id="ffd35-106">Die meisten der Beispiele in diesem Thema verwenden das folgende XSD-Schema:</span><span class="sxs-lookup"><span data-stu-id="ffd35-106">Most of the examples in this topic use the following XSD Schema:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
    <xsd:annotation>  
      <xsd:documentation>  
        Diffgram Customers/Orders Schema.  
      </xsd:documentation>  
      <xsd:appinfo>  
           <sql:relationship name="CustomersOrders"   
                      parent="Cust"  
                      parent-key="CustomerID"  
                      child-key="CustomerID"  
                      child="Ord"/>  
      </xsd:appinfo>  
    </xsd:annotation>  
  
    <xsd:element name="Customer" sql:relation="Cust">  
      <xsd:complexType>  
        <xsd:sequence>  
          <xsd:element name="CompanyName"    type="xsd:string"/>  
          <xsd:element name="ContactName"    type="xsd:string"/>  
           <xsd:element name="Order" sql:relation="Ord" sql:relationship="CustomersOrders">  
            <xsd:complexType>  
              <xsd:attribute name="OrderID" type="xsd:int" sql:field="OrderID"/>  
              <xsd:attribute name="CustomerID" type="xsd:string"/>  
            </xsd:complexType>  
          </xsd:element>  
        </xsd:sequence>  
        <xsd:attribute name="CustomerID" type="xsd:string" sql:field="CustomerID"/>  
      </xsd:complexType>  
    </xsd:element>  
  
    </xsd:schema>     
    ```  
  
     <span data-ttu-id="ffd35-107">Speichern Sie dieses Schema als DiffGramSchema.xml im gleichen Ordner, in dem Sie auch die anderen in diesem Beispiel verwendeten Dateien gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="ffd35-107">Save this schema as DiffGramSchema.xml in the same folder where you save other files used in the examples.</span></span>  
  
## <a name="a-deleting-a-record-by-using-a-diffgram"></a><span data-ttu-id="ffd35-108">A.</span><span class="sxs-lookup"><span data-stu-id="ffd35-108">A.</span></span> <span data-ttu-id="ffd35-109">Löschen eines Datensatzes mit einem DiffGram</span><span class="sxs-lookup"><span data-stu-id="ffd35-109">Deleting a record by using a DiffGram</span></span>  
 <span data-ttu-id="ffd35-110">Mit dem DiffGram in diesem Beispiel werden ein Kundendatensatz (mit der CustomerID ALFKI) aus der Cust-Tabelle und der entsprechende Auftragsdatensatz (mit der OrderID 1) aus der Ord-Tabelle gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ffd35-110">The DiffGram in this example deletes a customer (whose CustomerID is ALFKI) record from the Cust table and deletes the corresponding order record (whose OrderID is 1) from the Ord table.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
           xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
           xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance/>  
  
    <diffgr:before>  
        <Order diffgr:id="Order1"   
               msdata:rowOrder="0"   
               CustomerID="ALFKI"   
               OrderID="1"/>  
        <Customer diffgr:id="Customer1"   
                  msdata:rowOrder="0"   
                  CustomerID="ALFKI">  
           <CompanyName>Alfreds Futterkiste</CompanyName>  
           <ContactName>Maria Anders</ContactName>  
        </Customer>  
    </diffgr:before>  
    <msdata:errors/>  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="ffd35-111">Im- **\<before>** Block gibt es ein **\<Order>** -Element (**diffgr: ID = "order1"**) und ein- **\<Customer>** Element (**diffgr: ID = "Customer1"**).</span><span class="sxs-lookup"><span data-stu-id="ffd35-111">In the **\<before>** block, there is an **\<Order>** element (**diffgr:id="Order1"**) and a **\<Customer>** element (**diffgr:id="Customer1"**).</span></span> <span data-ttu-id="ffd35-112">Diese Elemente stellen vorhandene Datensätze in der Datenbank dar.</span><span class="sxs-lookup"><span data-stu-id="ffd35-112">These elements represent existing records in the database.</span></span> <span data-ttu-id="ffd35-113">Das- **\<DataInstance>** Element verfügt nicht über die entsprechenden Datensätze (mit der gleichen **diffgr: ID**).</span><span class="sxs-lookup"><span data-stu-id="ffd35-113">The **\<DataInstance>** element does not have the corresponding records (with the same **diffgr:id**).</span></span> <span data-ttu-id="ffd35-114">Dies gibt einen Löschvorgang an.</span><span class="sxs-lookup"><span data-stu-id="ffd35-114">This indicates a delete operation.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="ffd35-115">So testen Sie das DiffGram-Objekt</span><span class="sxs-lookup"><span data-stu-id="ffd35-115">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="ffd35-116">Erstellen Sie diese Tabellen in der **tempdb** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ffd35-116">Create these tables in the **tempdb** database.</span></span>  
  
    ```  
    CREATE TABLE Cust(  
            CustomerID  nchar(5) Primary Key,  
            CompanyName nvarchar(40) NOT NULL ,  
            ContactName nvarchar(60) NULL)  
    GO  
  
    CREATE TABLE Ord(  
       OrderID    int Primary Key,  
       CustomerID nchar(5) Foreign Key REFERENCES Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="ffd35-117">Fügen Sie diese Beispieldaten hinzu:</span><span class="sxs-lookup"><span data-stu-id="ffd35-117">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ALFKI', N'Alfreds Futterkiste', N'Maria Anders')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANATR', N'Ana Trujillo Emparedados y helados', N'Ana Trujillo')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANTON', N'Antonio Moreno Taquer??a', N'Antonio Moreno')  
  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(1, N'ALFKI')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(2, N'ANATR')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(3, N'ANTON')  
    ```  
  
3.  <span data-ttu-id="ffd35-118">Kopieren Sie das oben stehende DiffGram, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="ffd35-118">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="ffd35-119">Speichern Sie die Datei als MyDiffGram.xml in demselben Ordner, den Sie im vorherigen Schritt verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="ffd35-119">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="ffd35-120">Kopieren Sie das zuvor in diesem Thema bereitgestellte DiffGramSchema, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="ffd35-120">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="ffd35-121">Speichern Sie die Datei unter dem Dateinamen DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="ffd35-121">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="ffd35-122">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um das DiffGram auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ffd35-122">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="ffd35-123">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ffd35-123">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="b-inserting-a-record-by-using-a-diffgram"></a><span data-ttu-id="ffd35-124">B.</span><span class="sxs-lookup"><span data-stu-id="ffd35-124">B.</span></span> <span data-ttu-id="ffd35-125">Einfügen eines Datensatzes mit einem DiffGram</span><span class="sxs-lookup"><span data-stu-id="ffd35-125">Inserting a record by using a DiffGram</span></span>  
 <span data-ttu-id="ffd35-126">In diesem Beispiel fügt das DiffGram einen Datensatz in die Tabellen Cust und Ord ein.</span><span class="sxs-lookup"><span data-stu-id="ffd35-126">In this example, the DiffGram inserts a record in the Cust table and a record in the Ord table.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"   
      sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
          xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
          xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
       <Customer diffgr:id="Customer1" msdata:rowOrder="0"    
                 diffgr:hasChanges="inserted" CustomerID="ALFKI">  
        <CompanyName>C3Company</CompanyName>  
        <ContactName>C3Contact</ContactName>  
        <Order diffgr:id="Order1"   
               msdata:rowOrder="0"  
               diffgr:hasChanges="inserted"   
               CustomerID="ALFKI" OrderID="1"/>  
      </Customer>  
    </DataInstance>  
  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="ffd35-127">In diesem DiffGram wird der- **\<before>** Block nicht angegeben (es wurden keine vorhandenen Datenbank-Datensätze identifiziert).</span><span class="sxs-lookup"><span data-stu-id="ffd35-127">In this DiffGram the **\<before>** block is not specified (no existing database records identified).</span></span> <span data-ttu-id="ffd35-128">Es gibt zwei Daten Satz Instanzen (identifiziert durch das **\<Customer>** -Element und das- **\<Order>** Element im- **\<DataInstance>** Block), die den cust-bzw. Ord-Tabellen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ffd35-128">There are two record instances (identified by the **\<Customer>** and **\<Order>** elements in the **\<DataInstance>** block) that map to Cust and Ord tables, respectively.</span></span> <span data-ttu-id="ffd35-129">Beide Elemente geben das **diffgr: hasChanges** -Attribut an (**hasChanges = "eingefügt"**).</span><span class="sxs-lookup"><span data-stu-id="ffd35-129">Both of these elements specify the **diffgr:hasChanges** attribute (**hasChanges="inserted"**).</span></span> <span data-ttu-id="ffd35-130">Dies gibt einen Einfügevorgang an.</span><span class="sxs-lookup"><span data-stu-id="ffd35-130">This indicates an insert operation.</span></span> <span data-ttu-id="ffd35-131">Wenn Sie in diesem DiffGram **hasChanges = "modified"** angeben, geben Sie an, dass Sie einen nicht vorhandenen Datensatz ändern möchten. Dies führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="ffd35-131">In this DiffGram, if you specify **hasChanges="modified"**, you are indicating that you want to modify a record that does not exist, which results in an error.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="ffd35-132">So testen Sie das DiffGram-Objekt</span><span class="sxs-lookup"><span data-stu-id="ffd35-132">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="ffd35-133">Erstellen Sie diese Tabellen in der **tempdb** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ffd35-133">Create these tables in the **tempdb** database.</span></span>  
  
    ```  
    CREATE TABLE Cust(  
            CustomerID  nchar(5) Primary Key,  
            CompanyName nvarchar(40) NOT NULL ,  
            ContactName nvarchar(60) NULL)  
    GO  
  
    CREATE TABLE Ord(  
       OrderID    int Primary Key,  
       CustomerID nchar(5) Foreign Key REFERENCES Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="ffd35-134">Fügen Sie diese Beispieldaten hinzu:</span><span class="sxs-lookup"><span data-stu-id="ffd35-134">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ALFKI', N'Alfreds Futterkiste', N'Maria Anders')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANATR', N'Ana Trujillo Emparedados y helados', N'Ana Trujillo')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANTON', N'Antonio Moreno Taquer??a', N'Antonio Moreno')  
  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(1, N'ALFKI')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(2, N'ANATR')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(3, N'ANTON')  
    ```  
  
3.  <span data-ttu-id="ffd35-135">Kopieren Sie das oben stehende DiffGram, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="ffd35-135">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="ffd35-136">Speichern Sie die Datei als MyDiffGram.xml in demselben Ordner, den Sie im vorherigen Schritt verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="ffd35-136">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="ffd35-137">Kopieren Sie das zuvor in diesem Thema bereitgestellte DiffGramSchema, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="ffd35-137">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="ffd35-138">Speichern Sie die Datei unter dem Dateinamen DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="ffd35-138">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="ffd35-139">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um das DiffGram auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ffd35-139">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="ffd35-140">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ffd35-140">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="c-updating-an-existing-record-by-using-a-diffgram"></a><span data-ttu-id="ffd35-141">C.</span><span class="sxs-lookup"><span data-stu-id="ffd35-141">C.</span></span> <span data-ttu-id="ffd35-142">Aktualisieren eines vorhandenen Datensatzes mit einem DiffGram</span><span class="sxs-lookup"><span data-stu-id="ffd35-142">Updating an existing record by using a DiffGram</span></span>  
 <span data-ttu-id="ffd35-143">In diesem Beispiel aktualisiert das DiffGram Kundeninformationen (CompanyName und ContactName) für den Kunden ALFKI.</span><span class="sxs-lookup"><span data-stu-id="ffd35-143">In this example, the DiffGram updates customer information (CompanyName and ContactName) for customer ALFKI.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
           xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
           xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
      <Customer diffgr:id="Customer1"   
                msdata:rowOrder="0" diffgr:hasChanges="modified"   
                CustomerID="ALFKI">  
          <CompanyName>Bottom Dollar Markets</CompanyName>  
          <ContactName>Antonio Moreno</ContactName>  
      </Customer>  
    </DataInstance>  
  
    <diffgr:before>  
     <Customer diffgr:id="Customer1"   
               msdata:rowOrder="0"   
               CustomerID="ALFKI">  
        <CompanyName>Alfreds Futterkiste</CompanyName>  
        <ContactName>Maria Anders</ContactName>  
      </Customer>  
    </diffgr:before>  
  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="ffd35-144">Der- **\<before>** Block enthält ein- **\<Customer>** Element (**diffgr: ID = "Customer1"**).</span><span class="sxs-lookup"><span data-stu-id="ffd35-144">The **\<before>** block includes a **\<Customer>** element (**diffgr:id="Customer1"**).</span></span> <span data-ttu-id="ffd35-145">Der- **\<DataInstance>** Block enthält das entsprechende- **\<Customer>** Element mit derselben **ID**. Das- **\<customer>** Element in **\<NewDataSet>** gibt auch **diffgr: hasChanges = "modified"** an.</span><span class="sxs-lookup"><span data-stu-id="ffd35-145">The **\<DataInstance>** block includes the corresponding **\<Customer>** element with same **id**. The **\<customer>** element in the **\<NewDataSet>** also specifies **diffgr:hasChanges="modified"**.</span></span> <span data-ttu-id="ffd35-146">Dies weist auf einen Aktualisierungs Vorgang hin, und der Kundendaten Satz in der **cust** -Tabelle wird entsprechend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="ffd35-146">This indicates an update operation, and the customer record in the **Cust** table is updated accordingly.</span></span> <span data-ttu-id="ffd35-147">Beachten Sie Folgendes: Wenn das **diffgr: hasChanges** -Attribut nicht angegeben ist, ignoriert die DiffGram-Verarbeitungslogik dieses Element, und es werden keine Updates durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="ffd35-147">Note that if the **diffgr:hasChanges** attribute is not specified, the DiffGram processing logic ignores this element and no updates are performed.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="ffd35-148">So testen Sie das DiffGram-Objekt</span><span class="sxs-lookup"><span data-stu-id="ffd35-148">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="ffd35-149">Erstellen Sie diese Tabellen in der **tempdb** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ffd35-149">Create these tables in the **tempdb** database.</span></span>  
  
    ```  
    CREATE TABLE Cust(  
            CustomerID  nchar(5) Primary Key,  
            CompanyName nvarchar(40) NOT NULL ,  
            ContactName nvarchar(60) NULL)  
    GO  
  
    CREATE TABLE Ord(  
       OrderID    int Primary Key,  
       CustomerID nchar(5) Foreign Key REFERENCES Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="ffd35-150">Fügen Sie diese Beispieldaten hinzu:</span><span class="sxs-lookup"><span data-stu-id="ffd35-150">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ALFKI', N'Alfreds Futterkiste', N'Maria Anders')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANATR', N'Ana Trujillo Emparedados y helados', N'Ana Trujillo')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANTON', N'Antonio Moreno Taquer??a', N'Antonio Moreno')  
  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(1, N'ALFKI')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(2, N'ANATR')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(3, N'ANTON')  
    ```  
  
3.  <span data-ttu-id="ffd35-151">Kopieren Sie das oben stehende DiffGram, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="ffd35-151">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="ffd35-152">Speichern Sie die Datei als MyDiffGram.xml in demselben Ordner, den Sie im vorherigen Schritt verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="ffd35-152">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="ffd35-153">Kopieren Sie das zuvor in diesem Thema bereitgestellte DiffGramSchema, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="ffd35-153">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="ffd35-154">Speichern Sie die Datei unter dem Dateinamen DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="ffd35-154">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="ffd35-155">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um das DiffGram auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ffd35-155">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="ffd35-156">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ffd35-156">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="d-inserting-updating-and-deleting-records-by-using-a-diffgram"></a><span data-ttu-id="ffd35-157">D:</span><span class="sxs-lookup"><span data-stu-id="ffd35-157">D.</span></span> <span data-ttu-id="ffd35-158">Einfügen, Aktualisieren und Löschen von Datensätzen mit einem DiffGram</span><span class="sxs-lookup"><span data-stu-id="ffd35-158">Inserting, updating, and deleting records by using a DiffGram</span></span>  
 <span data-ttu-id="ffd35-159">In diesem Beispiel wird ein relativ komplexes DiffGram verwendet, um Einfüge-, Update- und Löschvorgänge durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ffd35-159">In this example, a relatively complex DiffGram is used to perform insert, update, and delete operations.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
      <Customer diffgr:id="Customer2" msdata:rowOrder="1"   
                diffgr:hasChanges="modified"   
                CustomerID="ANATR">  
          <CompanyName>Bottom Dollar Markets</CompanyName>  
          <ContactName>Elizabeth Lincoln</ContactName>  
          <Order diffgr:id="Order2" msdata:rowOrder="1"   
               msdata:hiddenCustomerID="ANATR"   
               CustomerID="ANATR" OrderID="2"/>  
      </Customer>  
  
      <Customer diffgr:id="Customer3" msdata:rowOrder="2"   
                CustomerID="ANTON">  
         <CompanyName>Chop-suey Chinese</CompanyName>  
         <ContactName>Yang Wang</ContactName>  
         <Order diffgr:id="Order3" msdata:rowOrder="2"   
               msdata:hiddenCustomerID="ANTON"   
               CustomerID="ANTON" OrderID="3"/>  
      </Customer>  
      <Customer diffgr:id="Customer4" msdata:rowOrder="3"   
                diffgr:hasChanges="inserted"   
                CustomerID="AROUT">  
         <CompanyName>Around the Horn</CompanyName>  
         <ContactName>Thomas Hardy</ContactName>  
         <Order diffgr:id="Order4" msdata:rowOrder="3"   
                diffgr:hasChanges="inserted"   
                msdata:hiddenCustomerID="AROUT"   
               CustomerID="AROUT" OrderID="4"/>  
      </Customer>  
    </DataInstance>  
    <diffgr:before>  
      <Order diffgr:id="Order1" msdata:rowOrder="0"   
             msdata:hiddenCustomerID="ALFKI"   
             CustomerID="ALFKI" OrderID="1"/>  
      <Customer diffgr:id="Customer1" msdata:rowOrder="0"   
                CustomerID="ALFKI">  
        <CompanyName>Alfreds Futterkiste</CompanyName>  
        <ContactName>Maria Anders</ContactName>  
      </Customer>  
      <Customer diffgr:id="Customer2" msdata:rowOrder="1"   
                CustomerID="ANATR">  
        <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
        <ContactName>Ana Trujillo</ContactName>  
      </Customer>  
    </diffgr:before>  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="ffd35-160">Die DiffGram-Logik verarbeitet dieses DiffGram folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="ffd35-160">The DiffGram logic processes this DiffGram as follows:</span></span>  
  
-   <span data-ttu-id="ffd35-161">In Übereinstimmung mit der DiffGram-Verarbeitungslogik werden alle Elemente der obersten Ebene im **\<before>** Block den entsprechenden Tabellen zugeordnet, wie im Zuordnungs Schema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ffd35-161">In accordance with DiffGram processing logic, all the top-level elements in the **\<before>** block map to corresponding tables, as described in the mapping schema.</span></span>  
  
-   <span data-ttu-id="ffd35-162">Der **\<before>** -Block verfügt über ein **\<Order>** -Element (**dffgr: ID = "order1"**) und ein- **\<Customer>** Element (**diffgr: ID = "Customer1"**), für das es kein entsprechendes Element im- **\<DataInstance>** Block (mit der gleichen ID) gibt.</span><span class="sxs-lookup"><span data-stu-id="ffd35-162">The **\<before>** block has an **\<Order>** element (**dffgr:id="Order1"**) and a **\<Customer>** element (**diffgr:id="Customer1"**) for which there is no corresponding element in the **\<DataInstance>** block (with the same ID).</span></span> <span data-ttu-id="ffd35-163">Dies gibt einen Löschvorgang an, und die Datensätze werden aus den Cust- und Ord-Tabellen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ffd35-163">This indicates a delete operation, and the records are deleted from the Cust and Ord tables.</span></span>  
  
-   <span data-ttu-id="ffd35-164">Der- **\<before>** Block verfügt über ein- **\<Customer>** Element (**diffgr: ID = "Customer2"**), für das es ein entsprechendes- **\<Customer>** Element im- **\<DataInstance>** Block (mit der gleichen ID) gibt.</span><span class="sxs-lookup"><span data-stu-id="ffd35-164">The **\<before>** block has a **\<Customer>** element (**diffgr:id="Customer2"**) for which there is a corresponding **\<Customer>** element in the **\<DataInstance>** block (with the same ID).</span></span> <span data-ttu-id="ffd35-165">Das-Element im- **\<DataInstance>** Block gibt **diffgr: hasChanges = "modified"** an.</span><span class="sxs-lookup"><span data-stu-id="ffd35-165">The element in the **\<DataInstance>** block specifies **diffgr:hasChanges="modified"**.</span></span> <span data-ttu-id="ffd35-166">Dabei handelt es sich um einen Update Vorgang, bei dem für Customer ANATR die Informationen CompanyName und ContactName in der Cust-Tabelle mithilfe der im-Block angegebenen Werte aktualisiert werden **\<DataInstance>** .</span><span class="sxs-lookup"><span data-stu-id="ffd35-166">This is an update operation in which for customer ANATR, the CompanyName and ContactName information is updated in the Cust table using values that are specified in the **\<DataInstance>** block.</span></span>  
  
-   <span data-ttu-id="ffd35-167">Der **\<DataInstance>** -Block verfügt über ein **\<Customer>** -Element (**diffgr: ID = "Customer3"**) und ein- **\<Order>** Element (**diffgr: ID = "Order3"**).</span><span class="sxs-lookup"><span data-stu-id="ffd35-167">The **\<DataInstance>** block has a **\<Customer>** element (**diffgr:id="Customer3"**) and an **\<Order>** element (**diffgr:id="Order3"**).</span></span> <span data-ttu-id="ffd35-168">Keines dieser Elemente gibt das **diffgr: hasChanges** -Attribut an.</span><span class="sxs-lookup"><span data-stu-id="ffd35-168">Neither of these elements specify the **diffgr:hasChanges** attribute.</span></span> <span data-ttu-id="ffd35-169">Daher ignoriert die DiffGram-Verarbeitungslogik diese Elemente.</span><span class="sxs-lookup"><span data-stu-id="ffd35-169">Therefore, the DiffGram processing logic ignores these elements.</span></span>  
  
-   <span data-ttu-id="ffd35-170">Der **\<DataInstance>** -Block verfügt über ein **\<Customer>** -Element (**diffgr: ID = "Customer4"**) und ein- **\<Order>** Element (**diffgr: ID = "Order4"**), für das es keine entsprechenden Elemente im- \<before> Block gibt.</span><span class="sxs-lookup"><span data-stu-id="ffd35-170">The **\<DataInstance>** block has a **\<Customer>** element (**diffgr:id="Customer4"**) and an **\<Order>** element (**diffgr:id="Order4"**) for which there are no corresponding elements in the \<before> block.</span></span> <span data-ttu-id="ffd35-171">Diese Elemente im- **\<DataInstance>** Block geben **diffgr: hasChanges = "eingefügt"** an.</span><span class="sxs-lookup"><span data-stu-id="ffd35-171">These elements in the **\<DataInstance>** block specify **diffgr:hasChanges="inserted"**.</span></span> <span data-ttu-id="ffd35-172">Daher wird ein neuer Datensatz der Cust-Tabelle und der Ord-Tabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ffd35-172">Therefore, a new record is added in the Cust table and in the Ord table.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="ffd35-173">So testen Sie das DiffGram-Objekt</span><span class="sxs-lookup"><span data-stu-id="ffd35-173">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="ffd35-174">Erstellen Sie die folgenden Tabellen in der **tempdb** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ffd35-174">Create the following tables in the **tempdb** database.</span></span>  
  
    ```  
    CREATE TABLE Cust(  
            CustomerID  nchar(5) Primary Key,  
            CompanyName nvarchar(40) NOT NULL ,  
            ContactName nvarchar(60) NULL)  
    GO  
  
    CREATE TABLE Ord(  
       OrderID    int Primary Key,  
       CustomerID nchar(5) Foreign Key REFERENCES Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="ffd35-175">Fügen Sie diese Beispieldaten hinzu:</span><span class="sxs-lookup"><span data-stu-id="ffd35-175">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ALFKI', N'Alfreds Futterkiste', N'Maria Anders')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANATR', N'Ana Trujillo Emparedados y helados', N'Ana Trujillo')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANTON', N'Antonio Moreno Taquer??a', N'Antonio Moreno')  
  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(1, N'ALFKI')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(2, N'ANATR')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(3, N'ANTON')  
    ```  
  
3.  <span data-ttu-id="ffd35-176">Kopieren Sie das oben stehende DiffGram, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="ffd35-176">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="ffd35-177">Speichern Sie die Datei als MyDiffGram.xml in demselben Ordner, den Sie im vorherigen Schritt verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="ffd35-177">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="ffd35-178">Kopieren Sie das zuvor in diesem Thema bereitgestellte DiffGramSchema, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="ffd35-178">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="ffd35-179">Speichern Sie die Datei unter dem Dateinamen DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="ffd35-179">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="ffd35-180">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um das DiffGram auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ffd35-180">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="ffd35-181">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ffd35-181">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="e-applying-updates-by-using-a-diffgram-with-the-diffgrparentid-annotation"></a><span data-ttu-id="ffd35-182">E.</span><span class="sxs-lookup"><span data-stu-id="ffd35-182">E.</span></span> <span data-ttu-id="ffd35-183">Übernehmen von Updates mit einem DiffGram mit der "diffgr:parentID"-Anmerkung</span><span class="sxs-lookup"><span data-stu-id="ffd35-183">Applying updates by using a DiffGram with the diffgr:parentID annotation</span></span>  
 <span data-ttu-id="ffd35-184">In diesem Beispiel wird veranschaulicht, wie die im-Block des DiffGram-Blocks angegebene " **Parser-** ID"-Anmerkung zum **\<before>** Anwenden der Updates verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ffd35-184">This example illustrates how the **parentID** annotation that is specified in the **\<before>** block of the DiffGram is used in applying the updates.</span></span>  
  
```  
<NewDataSet />  
<diffgr:before>  
   <Order diffgr:id="Order1" msdata:rowOrder="0" OrderID="2" />  
   <Order diffgr:id="Order3" msdata:rowOrder="2" OrderID="4" />  
  
   <OrderDetail diffgr:id="OrderDetail1"   
                diffgr:parentId="Order1"   
                msdata:rowOrder="0"   
                ProductID="13"   
                OrderID="2" />  
   <OrderDetail diffgr:id="OrderDetail3"   
                diffgr:parentId="Order3"  
                ProductID="77"  
                OrderID="4"/>  
</diffgr:before>  
</diffgr:diffgram>  
```  
  
 <span data-ttu-id="ffd35-185">Dieses DiffGram gibt einen Löschvorgang an, da nur ein-Block vorhanden ist **\<before>** .</span><span class="sxs-lookup"><span data-stu-id="ffd35-185">This DiffGram specifies a delete operation because there is only a **\<before>** block.</span></span> <span data-ttu-id="ffd35-186">Im DiffGram wird die Element **-** ID-Anmerkung verwendet, um eine über-/Unterordnungsbeziehung zwischen den Bestellungen und Bestelldetails anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ffd35-186">In the DiffGram, the **parentID** annotation is used to specify a parent-child relationship between the orders and order details.</span></span> <span data-ttu-id="ffd35-187">Wenn SQLXML die Datensätze löscht, werden auch die Datensätze aus der untergeordneten Tabelle, die durch diese Beziehung gekennzeichnet wird, gelöscht. Anschließend werden die Datensätze aus der entsprechenden übergeordneten Tabelle gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ffd35-187">When SQLXML deletes the records, it deletes records from the child table that is identified by this relationship and then deletes the records from the corresponding parent table.</span></span>  
  
  
