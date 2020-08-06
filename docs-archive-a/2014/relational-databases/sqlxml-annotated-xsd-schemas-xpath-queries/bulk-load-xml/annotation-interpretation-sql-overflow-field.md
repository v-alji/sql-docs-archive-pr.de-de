---
title: 'SQL: overflow-field (SQLXML 4,0) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- overflow-field annotation
- unconsumed data
- overflow data [SQLXML]
- sql:overflow-field
ms.assetid: f005182b-6151-432d-ab22-3bc025742cd3
author: rothja
ms.author: jroth
ms.openlocfilehash: ea52eb642964844a03304d082632c2b7157f723b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619757"
---
# <a name="sqloverflow-field-sqlxml-40"></a><span data-ttu-id="7f3e2-102">sql:overflow-field (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="7f3e2-102">sql:overflow-field (SQLXML 4.0)</span></span>
  <span data-ttu-id="7f3e2-103">In einem Schema können Sie eine Spalte als Überlaufspalte festlegen, die alle nicht verbrauchten Daten aus dem XML-Dokument aufnimmt.</span><span class="sxs-lookup"><span data-stu-id="7f3e2-103">In a schema, you can identify a column as an overflow column to receive all unconsumed data from the XML document.</span></span> <span data-ttu-id="7f3e2-104">Diese Spalte wird im Schema mithilfe der `sql:overflow-field`-Anmerkung angegeben.</span><span class="sxs-lookup"><span data-stu-id="7f3e2-104">This column is specified in the schema by using the `sql:overflow-field` annotation.</span></span> <span data-ttu-id="7f3e2-105">Sie können mit mehreren Überlaufspalten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="7f3e2-105">It is possible to have multiple overflow columns.</span></span>  
  
 <span data-ttu-id="7f3e2-106">Immer, wenn ein XML-Knoten (Element oder Attribut), für den eine `sql:overflow-field`-Anmerkung definiert ist, in den Bereich eintritt, wird die Überlaufspalte aktiviert und empfängt nicht verbrauchte Daten.</span><span class="sxs-lookup"><span data-stu-id="7f3e2-106">Whenever an XML node (element or attribute) for which there is a `sql:overflow-field` annotation defined enters into scope, the overflow column is activated and receives unconsumed data.</span></span> <span data-ttu-id="7f3e2-107">Wenn der Knoten den Bereich verlässt, ist die Überlaufspalte nicht mehr aktiv und das vorherige Überlauffeld (sofern vorhanden) wird durch das XML-Massenladen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7f3e2-107">When the node goes out of scope, the overflow column is no longer active and XML Bulk Load makes the previous overflow field (if any) active.</span></span>  
  
 <span data-ttu-id="7f3e2-108">Bei der Speicherung der Daten in der Überlaufspalte speichert der XML-Massenladevorgang ebenfalls die Start- und Endtags des übergeordneten Elements, für das `sql:overflow-field` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="7f3e2-108">As it stores data in the overflow column, XML Bulk Load also stores the opening and closing tags of the parent element for which `sql:overflow-field` is defined.</span></span>  
  
 <span data-ttu-id="7f3e2-109">Im folgenden Schema werden z **\<Customers>** . b. die-und- **\<CustOrder>** Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7f3e2-109">For example, the following schema describes the **\<Customers>** and **\<CustOrder>** elements.</span></span> <span data-ttu-id="7f3e2-110">Beide Elemente geben eine Überlaufspalte an:</span><span class="sxs-lookup"><span data-stu-id="7f3e2-110">Each of these elements identifies an overflow column:</span></span>  
  
```  
<?xml version="1.0" ?>  
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
 <xsd:element name="ROOT" sql:is-constant="1">  
  <xsd:complexType>  
    <xsd:sequence>   
      <xsd:element name="Customers"   
                   sql:relation="Cust"  
                   sql:overflow-field="OverflowColumn">  
        <xsd:complexType>  
             <xsd:sequence>   
             <xsd:element name="CustomerID" type="xsd:integer"/>  
             <xsd:element name="CompanyName"  type="xsd:string"/>  
             <xsd:element name="City" type="xsd:string"/>  
             <xsd:element name="Order"  
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder"  
                          sql:overflow-field="OverflowColumn">  
               <xsd:complexType>  
                 <xsd:attribute name="OrderID"/>  
                 <xsd:attribute name="CustomerID"/>  
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
  
 <span data-ttu-id="7f3e2-111">Im Schema wird das **\<Customer>** -Element der Cust-Tabelle und das- **\<Order>** Element der CustOrder-Tabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7f3e2-111">In the schema, the **\<Customer>** element maps to the Cust table and the **\<Order>** element maps to the CustOrder table.</span></span>  
  
 <span data-ttu-id="7f3e2-112">Sowohl das **\<Customer>** -Element als auch das- **\<Order>** Element identifizieren eine Überlauf Spalte.</span><span class="sxs-lookup"><span data-stu-id="7f3e2-112">Both the **\<Customer>** and **\<Order>** elements identify an overflow column.</span></span> <span data-ttu-id="7f3e2-113">Folglich speichert XML-Massen laden alle nicht verbrauchten untergeordneten Elemente und Attribute des- **\<Customer>** Elements in der Überlauf Spalte der Cust-Tabelle und alle nicht verbrauchten untergeordneten Elemente und Attribute des- **\<Order>** Elements in der Überlauf Spalte der CustOrder-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7f3e2-113">Thus, XML Bulk Load saves all the unconsumed child elements and attributes of the **\<Customer>** element in the overflow column of the Cust table, and all the unconsumed child elements and attributes of the **\<Order>** element in the overflow column of the CustOrder table.</span></span>  
  
### <a name="to-test-a-working-sample"></a><span data-ttu-id="7f3e2-114">So testen Sie ein funktionstüchtiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="7f3e2-114">To test a working sample</span></span>  
  
1.  <span data-ttu-id="7f3e2-115">Speichern Sie das in diesem Beispiel bereitgestellte Schema unter dem Dateinamen SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="7f3e2-115">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
2.  <span data-ttu-id="7f3e2-116">Erstellen Sie die folgenden Tabellen:</span><span class="sxs-lookup"><span data-stu-id="7f3e2-116">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
              CustomerID     int         PRIMARY KEY,  
              CompanyName    varchar(20) NOT NULL,  
              City           varchar(20) DEFAULT 'Seattle',  
              OverflowColumn nvarchar(200))  
    GO  
    CREATE TABLE CustOrder (  
              OrderID        int         PRIMARY KEY,  
              CustomerID     int         FOREIGN KEY REFERENCES  
                                              Cust(CustomerID),  
              OverflowColumn nvarchar(200))  
    GO  
    ```  
  
3.  <span data-ttu-id="7f3e2-117">Speichern Sie die folgenden XML-Daten unter dem Dateinamen SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="7f3e2-117">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
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
       <City><![CDATA[LA]]> </City>  
       <xyz><address>111 Maple, Seattle</address></xyz>     
       <Order OrderID="3" />  
     </Customers>  
       <Customers>  
       <CustomerID>1113</CustomerID>  
       <CompanyName>Victuailles en stock</CompanyName>  
       <Order OrderID="4" />  
      </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="7f3e2-118">Speichern Sie dieses [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition-Beispiel (VBScript) unter dem Dateinamen Sample.vbs, und führen Sie es aus, um das XML-Massenladen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="7f3e2-118">To execute XML Bulk Load, save and execute this [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example as Sample.vbs:</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
  
