---
title: Ausführen von XPath-Abfragen (SQLXMLOLEDB-Anbieter) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, executing XPath queries
- queries [SQLXML], SQLXMLOLEDB Provider
- Base Path property
- XPath queries [SQLXML], SQLXMLOLEDB Provider
- Mapping Schema property
ms.assetid: 19063222-dc9c-48ae-a55f-778103674a9e
author: rothja
ms.author: jroth
ms.openlocfilehash: 667bc8dfd95c37c0a10c0bc68f3007e7d04533e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700910"
---
# <a name="executing-xpath-queries-sqlxmloledb-provider"></a><span data-ttu-id="5d907-102">Ausführen von XPath-Abfragen (SQLXMLOLEDB-Anbieter)</span><span class="sxs-lookup"><span data-stu-id="5d907-102">Executing XPath Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="5d907-103">Dieses Beispiel veranschaulicht die Verwendung der folgenden SQLXMLOLEDB-anbieterspezifischen Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="5d907-103">This example illustrates the use of the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   `ClientSideXML`  
  
-   `Base Path`  
  
-   `Mapping Schema`  
  
 <span data-ttu-id="5d907-104">In dieser Beispiel-ADO-Anwendung wird eine XPath-Abfrage (Stamm) mit einem XSD-Zuordnungsschema (MySchema.xml) angegeben.</span><span class="sxs-lookup"><span data-stu-id="5d907-104">In this sample ADO application, an XPath query (root) is specified against an XSD mapping schema (MySchema.xml).</span></span> <span data-ttu-id="5d907-105">Das Schema verfügt über ein- **\<Contacts>** Element mit den Attributen **ContactID**, **FirstName**und **LastName** .</span><span class="sxs-lookup"><span data-stu-id="5d907-105">The schema has a **\<Contacts>** element with **ContactID**, **FirstName**, and **LastName** attributes.</span></span> <span data-ttu-id="5d907-106">Im Schema wird die Standardzuordnung verwendet: ein Elementname wird der gleichnamigen Tabelle zugeordnet, und die Attribute eines einfachen Typs werden den gleichnamigen Spalten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="5d907-106">In the schema, default mapping takes place: an element name maps to the table with the same name, and attributes of simple type map to the columns with the same names.</span></span>  
  
```  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
   xmlns:sql='urn:schemas-microsoft-com:mapping-schema'>  
 <xsd:element name= 'root' sql:is-constant='1'>   
    <xsd:complexType>  
       <xsd:sequence>  
         <xsd:element ref = 'Contacts'/>  
       </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
  <xsd:element name='Contacts' sql:relation='Person.Contact'>   
     <xsd:complexType>  
          <xsd:attribute name='ContactID' type='xsd:integer' />  
          <xsd:attribute name='FirstName' type='xsd:string'/>   
          <xsd:attribute name='LastName' type='xsd:string' />   
     </xsd:complexType>  
   </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="5d907-107">Die Mapping-Schema Eigenschaft stellt das Zuordnungsschema bereit, für das die XPath-Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5d907-107">The Mapping Schema property provides the mapping schema against which the XPath query is executed.</span></span> <span data-ttu-id="5d907-108">Das Zuordnungsschema kann ein XSD- oder ein XDR-Schema sein.</span><span class="sxs-lookup"><span data-stu-id="5d907-108">The mapping schema can be an XSD or XDR schema.</span></span> <span data-ttu-id="5d907-109">Die Eigenschaft Basispfad stellt den Dateipfad zum Zuordnungsschema bereit.</span><span class="sxs-lookup"><span data-stu-id="5d907-109">The Base Path property provides the file path to the mapping schema.</span></span>  
  
 <span data-ttu-id="5d907-110">Die ClientSideXML-Eigenschaft ist auf true festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5d907-110">The ClientSideXML property is set to True.</span></span> <span data-ttu-id="5d907-111">Deshalb wird das XML-Dokument auf dem Client generiert.</span><span class="sxs-lookup"><span data-stu-id="5d907-111">Therefore, the XML document is generated on the client.</span></span>  
  
 <span data-ttu-id="5d907-112">In der Anwendung wird eine XPath-Abfrage direkt angegeben.</span><span class="sxs-lookup"><span data-stu-id="5d907-112">In the application, an XPath query is specified directly.</span></span> <span data-ttu-id="5d907-113">Deshalb muss der XPath-Dialekt {ec2a4293-e898-11d2-b1b7-00c04f680c56} eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="5d907-113">Therefore, the XPath dialect {ec2a4293-e898-11d2-b1b7-00c04f680c56} must be included.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d907-114">Im Code müssen Sie den Namen der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der Verbindungszeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5d907-114">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="5d907-115">In diesem Beispiel wird überdies die Verwendung von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) als Datenanbieter beschrieben, was die Installation zusätzlicher Netzwerkclientsoftware erforderlich macht.</span><span class="sxs-lookup"><span data-stu-id="5d907-115">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="5d907-116">Weitere Informationen finden Sie unter [System Anforderungen für SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="5d907-116">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security= SSPI;"  
  
oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
  
oTestCommand.CommandText = "root"  
oTestStream.Open  
oTestCommand.Dialect = "{ec2a4293-e898-11d2-b1b7-00c04f680c56}"  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("Base Path").Value = "c:\Schemas\SQLXML4\XPathDirect\"  
oTestCommand.Properties("Mapping Schema").Value = "mySchema.xml"  
oTestCommand.Properties("Output Encoding") = "utf-8"  
oTestCommand.Execute , , adExecuteStream  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
  
