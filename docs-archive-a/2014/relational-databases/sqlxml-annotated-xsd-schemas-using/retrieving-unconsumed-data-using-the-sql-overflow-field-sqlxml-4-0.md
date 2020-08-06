---
title: "Abrufen von nicht verbrauchten Daten mithilfe von ' SQL: overflow-field ' (SQLXML 4,0) | Microsoft-Dokumentation"
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- unconsumed data
- storing unconsumed data
- retrieving unconsumed data
- annotated XSD schemas, unconsumed data
- overflow data [SQLXML]
- sql:overflow-field
ms.assetid: 8526998d-b47d-4a32-8dc2-7f50a8d11097
author: rothja
ms.author: jroth
ms.openlocfilehash: 796fda9428954c5f18c5d37b353de9fd4122551e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621425"
---
# <a name="retrieving-unconsumed-data-using-the-sqloverflow-field-sqlxml-40"></a><span data-ttu-id="e91df-102">Abrufen von nicht verbrauchten Daten mithilfe von 'sql:overflow-field' (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e91df-102">Retrieving Unconsumed Data Using the sql:overflow-field (SQLXML 4.0)</span></span>
  <span data-ttu-id="e91df-103">Wenn Datensätze mithilfe der [!INCLUDE[tsql](../../includes/tsql-md.md)] OPENXML-Funktion aus einem XML-Dokument in eine Datenbank eingefügt werden, können alle nicht verbrauchten Daten aus dem XML-Quelldokument in einer Spalte gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e91df-103">When records are inserted in a database from an XML document by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] OPENXML function, all the unconsumed data from the source XML document can be stored in a column.</span></span> <span data-ttu-id="e91df-104">Beim Abrufen von Daten aus einer Datenbank mithilfe von Schemas mit Anmerkungen können Sie das `sql:overflow-field`-Attribut angeben, um die Spalte in der Tabelle zu identifizieren, in der die Überlaufdaten gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="e91df-104">When you retrieve data from a database by using annotated schemas, you can specify the `sql:overflow-field` attribute to identify the column in the table in which the overflow data is stored.</span></span> <span data-ttu-id="e91df-105">Das- `sql:overflow-field` Attribut kann für angegeben werden **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="e91df-105">The `sql:overflow-field` attribute can be specified on **\<element>**.</span></span>  
  
 <span data-ttu-id="e91df-106">Anschließend gibt es folgende Möglichkeiten, diese Daten abzurufen:</span><span class="sxs-lookup"><span data-stu-id="e91df-106">This data is then retrieved in these ways:</span></span>  
  
-   <span data-ttu-id="e91df-107">Attribute, die in der Überlaufspalte gespeichert sind, werden dem Element hinzugefügt, das die `sql:overflow-field`-Anmerkung enthält.</span><span class="sxs-lookup"><span data-stu-id="e91df-107">Attributes stored in the overflow column are added to the element that contains the `sql:overflow-field` annotation.</span></span>  
  
-   <span data-ttu-id="e91df-108">Die untergeordneten Elemente und ihre Nachfolger, die in der Überlaufspalte der Datenbank gespeichert sind, werden nach dem im Schema explizit angegebenen Inhalt als untergeordnete Elemente hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e91df-108">The child elements and their descendents, stored in the overflow column in the database, are added as child elements following the content that is explicitly specified in the schema.</span></span> <span data-ttu-id="e91df-109">(Die Reihenfolge wird nicht beibehalten.)</span><span class="sxs-lookup"><span data-stu-id="e91df-109">(No order is preserved.)</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e91df-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e91df-110">Examples</span></span>  
 <span data-ttu-id="e91df-111">Es müssen bestimmte Anforderungen erfüllt sein, damit aus den folgenden Beispielen funktionierende Beispiele erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="e91df-111">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="e91df-112">Weitere Informationen finden Sie unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="e91df-112">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqloverflow-field-for-an-element"></a><span data-ttu-id="e91df-113">A.</span><span class="sxs-lookup"><span data-stu-id="e91df-113">A.</span></span> <span data-ttu-id="e91df-114">Angeben von "sql:overflow-field" für ein Element</span><span class="sxs-lookup"><span data-stu-id="e91df-114">Specifying sql:overflow-field for an element</span></span>  
 <span data-ttu-id="e91df-115">Im folgenden Beispiel wird vorausgesetzt, dass das folgende Skript ausgeführt wurde, damit eine Tabelle mit dem Namen Customers2 in der tempdb-Datenbank vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="e91df-115">This example assumes that the following script has been run so that a table named Customers2 exists in the tempdb database:</span></span>  
  
```  
USE tempdb  
CREATE TABLE Customers2 (  
CustomerID       VARCHAR(10),   
ContactName    VARCHAR(30),   
AddressOverflow    NVARCHAR(500))  
  
GO  
INSERT INTO Customers2 VALUES (  
'ALFKI',   
'Joe',  
'<Address>  
  <Address1>Maple St.</Address1>  
  <Address2>Apt. E105</Address2>  
  <City>Seattle</City>  
  <State>WA</State>  
  <Zip>98147</Zip>  
 </Address>')  
GO  
```  
  
 <span data-ttu-id="e91df-116">Außerdem müssen Sie ein virtuelles Verzeichnis für die tempdb-Datenbank und einen virtuellen Vorlagen Namen vom `template` Typ "Template" erstellen.</span><span class="sxs-lookup"><span data-stu-id="e91df-116">In addition, you must create a virtual directory for the tempdb database-and a template virtual name of `template` type named "template".</span></span>  
  
 <span data-ttu-id="e91df-117">Im folgenden Beispiel ruft das Zuordnungsschema die nicht verbrauchten Daten ab, die in der Spalte AddressOverflow der Tabelle Customers2 gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="e91df-117">In the following example, the mapping schema retrieves the unconsumed data that is stored in the AddressOverflow column of the Customers2 table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Customers2" sql:overflow-field="AddressOverflow" >  
    <xsd:complexType>  
      <xsd:attribute name="CustomerID"  type="xsd:integer"/>  
      <xsd:attribute name="ContactName"  type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e91df-118">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="e91df-118">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e91df-119">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="e91df-119">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="e91df-120">Speichern Sie die Datei unter dem Dateinamen Overflow.xml.</span><span class="sxs-lookup"><span data-stu-id="e91df-120">Save the file as Overflow.xml.</span></span>  
  
2.  <span data-ttu-id="e91df-121">Kopieren Sie die folgende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="e91df-121">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="e91df-122">Speichern Sie die Datei unter dem Namen OverflowT.xml im gleichen Verzeichnis, in dem Sie Overflow.xml gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="e91df-122">Save the file as OverflowT.xml in the same directory where you saved Overflow.xml.</span></span> <span data-ttu-id="e91df-123">Die Abfrage in der Vorlage wählt die Datensätze in der Customers2-Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="e91df-123">The query in the template selects the records in the Customers2 table.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="Overflow.xml">  
            /Customers2  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e91df-124">Der für das Zuordnungsschema (Overflow.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="e91df-124">The directory path specified for the mapping schema (Overflow.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e91df-125">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e91df-125">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\Overflow.xml"  
    ```  
  
3.  <span data-ttu-id="e91df-126">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e91df-126">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e91df-127">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e91df-127">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e91df-128">Im Folgenden wird das Resultset aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="e91df-128">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customers2 CustomerID="ALFKI" ContactName="Joe">  
    <Address1>Maple St.</Address1>   
    <Address2>Apt. E105</Address2>   
    <City>Seattle</City>   
    <State>WA</State>   
    <Zip>98147</Zip>   
  </Customers2>  
</ROOT>  
```  
  
  
