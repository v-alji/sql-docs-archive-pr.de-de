---
title: Ausführen eines DiffGram-Codes mithilfe von verwalteten SQLXML-Klassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], Managed Classes
- SQLXML Managed Classes, DiffGrams
- Managed Classes [SQLXML], DiffGrams
- SQLXML, Managed Classes
ms.assetid: 81c687ca-8c9f-4f58-801f-8dabcc508a06
author: rothja
ms.author: jroth
ms.openlocfilehash: f36127c37eea73a2872d4bf0aef7172a88e430a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618592"
---
# <a name="executing-a-diffgram-by-using-sqlxml-managed-classes"></a><span data-ttu-id="d1f54-102">Ausführen eines DiffGram-Objekts mit verwalteten SQLXML-Klassen</span><span class="sxs-lookup"><span data-stu-id="d1f54-102">Executing a DiffGram by Using SQLXML Managed Classes</span></span>
  <span data-ttu-id="d1f54-103">Dieses Beispiel zeigt, wie Sie eine DiffGram-Datei in der [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework Umgebung ausführen, um Datenaktualisierungen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mithilfe von verwalteten SQLXML-Klassen (Microsoft. Data. SqlXml) auf Tabellen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="d1f54-103">This example shows how to execute a DiffGram file in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework environment to apply data updates to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables using SQLXML Managed Classes (Microsoft.Data.SqlXml).</span></span>  
  
 <span data-ttu-id="d1f54-104">In diesem Beispiel aktualisiert das DiffGram Kundeninformationen (CompanyName und ContactName) für den Kunden ALFKI.</span><span class="sxs-lookup"><span data-stu-id="d1f54-104">In this example, the DiffGram updates customer information (CompanyName and ContactName) for customer ALFKI.</span></span>  
  
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
  
 <span data-ttu-id="d1f54-105">Der- **\<before>** Block enthält ein- **\<Customer>** Element (**diffgr: ID = "Customer1"**).</span><span class="sxs-lookup"><span data-stu-id="d1f54-105">The **\<before>** block includes a **\<Customer>** element (**diffgr:id="Customer1"**).</span></span> <span data-ttu-id="d1f54-106">Der- **\<DataInstance>** Block enthält das entsprechende- **\<Customer>** Element mit derselben **ID**. Das- **\<customer>** Element in **\<NewDataSet>** gibt auch **diffgr: hasChanges = "modified"** an.</span><span class="sxs-lookup"><span data-stu-id="d1f54-106">The **\<DataInstance>** block includes the corresponding **\<Customer>** element with same **id**. The **\<customer>** element in the **\<NewDataSet>** also specifies **diffgr:hasChanges="modified"**.</span></span> <span data-ttu-id="d1f54-107">Dadurch wird ein Updatevorgang angezeigt und der Kundendatensatz in der Cust-Tabelle entsprechend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="d1f54-107">This indicates an update operation, and the customer record in the Cust table is updated accordingly.</span></span> <span data-ttu-id="d1f54-108">Beachten Sie Folgendes: Wenn das **diffgr: hasChanges** -Attribut nicht angegeben ist, ignoriert die DiffGram-Verarbeitungslogik dieses Element, und es werden keine Updates durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="d1f54-108">Note that if the **diffgr:hasChanges** attribute is not specified, the DiffGram processing logic ignores this element and no updates are performed.</span></span>  
  
 <span data-ttu-id="d1f54-109">Der folgende Code zeigt eine c#-Lernprogramm Anwendung, die veranschaulicht, wie die verwalteten SQLXML-Klassen verwendet werden, um das obige DiffGram auszuführen und zwei Tabellen (cust, Ord) zu aktualisieren, die Sie ebenfalls in der **tempdb** -Datenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1f54-109">The following is code for a C# tutorial application that shows how to use the SQLXML Managed Classes to execute the above DiffGram and update two tables (Cust, Ord) you will also create in the **tempdb** database.</span></span>  
  
```  
using System;  
using System.Data;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=MyServer;database=tempdb;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      SqlXmlAdapter ad;  
      // Need a memory stream to hold diff gram temporarily  
      MemoryStream ms = new MemoryStream();  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.RootTag = "ROOT";  
      cmd.CommandStream = new FileStream("MyDiffgram.xml", FileMode.Open, FileAccess.Read);  
      cmd.CommandType = SqlXmlCommandType.DiffGram;  
      cmd.SchemaPath = "DiffGramSchema.xml";  
      // Load data set  
      DataSet ds = new DataSet();  
      ad = new SqlXmlAdapter(cmd);  
      ad.Fill(ds);  
      ad.Update(ds);  
      return 0;  
   }  
   public static int Main(String[] args)  
   {  
      testParams();  
      return 0;  
   }  
}  
```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="d1f54-110">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="d1f54-110">To test the application</span></span>  
  
1.  <span data-ttu-id="d1f54-111">Stellen Sie sicher, dass .NET Framework auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="d1f54-111">Ensure that the .NET Framework is installed on your computer.</span></span>  
  
2.  <span data-ttu-id="d1f54-112">Speichern Sie das folgende XSD-Schema (DiffGramSchema.xml) in einem Ordner:</span><span class="sxs-lookup"><span data-stu-id="d1f54-112">Save the following XSD schema (DiffGramSchema.xml) in a folder:</span></span>  
  
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
  
3.  <span data-ttu-id="d1f54-113">Erstellen Sie diese Tabellen in der **tempdb** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d1f54-113">Create these tables in the **tempdb** database.</span></span>  
  
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
  
4.  <span data-ttu-id="d1f54-114">Fügen Sie diese Beispieldaten hinzu:</span><span class="sxs-lookup"><span data-stu-id="d1f54-114">Add this sample data:</span></span>  
  
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
  
5.  <span data-ttu-id="d1f54-115">Kopieren Sie das oben stehende DiffGram, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="d1f54-115">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="d1f54-116">Speichern Sie die Datei als MyDiffGram.xml in demselben Ordner, den Sie in Schritt 1 verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="d1f54-116">Save the file as MyDiffGram.xml in the same folder used in step 1.</span></span>  
  
6.  <span data-ttu-id="d1f54-117">Speichern Sie den C#-Code (DiffgramSample.cs) aus dem Beispiel oben im selben Ordner, in dem DiffGramSchema.xml und MyDiffGram.xml aus den vorherigen Schritten gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="d1f54-117">Save the C# code (DiffgramSample.cs) that is provided above in the same folder in which the DiffGramSchema.xml and MyDiffGram.xml were stored in previous steps.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d1f54-118">Sie müssen den Namen der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz in der Verbindungszeichenfolge von '`MyServer`' in den tatsächlichen Namen Ihrer installierten Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ändern.</span><span class="sxs-lookup"><span data-stu-id="d1f54-118">You will need to update the name of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the connection string from '`MyServer`' to the actual name of your installed instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="d1f54-119">Wenn Sie die Dateien in einem anderen Ordner speichern, müssen Sie den Code bearbeiten und den entsprechenden Verzeichnispfad für das Zuordnungsschema angeben.</span><span class="sxs-lookup"><span data-stu-id="d1f54-119">If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.</span></span>  
  
7.  <span data-ttu-id="d1f54-120">Kompilieren Sie den Code.</span><span class="sxs-lookup"><span data-stu-id="d1f54-120">Compile the code.</span></span> <span data-ttu-id="d1f54-121">Verwenden Sie zur Kompilierung des Codes an der Eingabeaufforderung die folgende Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="d1f54-121">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DiffgramSample.cs  
    ```  
  
     <span data-ttu-id="d1f54-122">Dadurch wird eine ausführbare Datei (DiffgramSample.exe) erstellt.</span><span class="sxs-lookup"><span data-stu-id="d1f54-122">This creates an executable (DiffgramSample.exe).</span></span>  
  
8.  <span data-ttu-id="d1f54-123">Führen Sie DiffgramSample.exe an der Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="d1f54-123">At the command prompt, execute DiffgramSample.exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1f54-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d1f54-124">See Also</span></span>  
 [<span data-ttu-id="d1f54-125">DiffGram-Beispiele &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d1f54-125">DiffGram Examples &#40;SQLXML 4.0&#41;</span></span>](diffgram-examples-sqlxml-4-0.md)  
  
  
