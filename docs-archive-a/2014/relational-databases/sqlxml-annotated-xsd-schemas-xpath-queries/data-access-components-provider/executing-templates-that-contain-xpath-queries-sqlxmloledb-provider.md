---
title: Ausführen von Vorlagen, die XPath-Abfragen enthalten (SQLXMLOLEDB-Anbieter) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, executing template files
- Base Path property
- templates [SQLXML], XPath queries
- XPath queries [SQLXML], templates
- XPath queries [SQLXML], SQLXMLOLEDB Provider
- Mapping Schema property
- XML templates [SQLXML]
ms.assetid: 7368c188-607e-459e-8254-8f23352dfa01
author: rothja
ms.author: jroth
ms.openlocfilehash: b3d31c95fe5d4fb1b7dc9a8d039a56b41cdd7349
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700905"
---
# <a name="executing-templates-that-contain-xpath-queries-sqlxmloledb-provider"></a><span data-ttu-id="25d28-102">Ausführen von Vorlagen, die XPath-Abfragen enthalten (SQLXMLOLEDB-Anbieter)</span><span class="sxs-lookup"><span data-stu-id="25d28-102">Executing Templates That Contain XPath Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="25d28-103">In diesem Beispiel wird gezeigt, wie die folgenden für den SQLXMLOLEDB-Anbieter spezifischen Eigenschaften verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="25d28-103">This example shows how to use the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   <span data-ttu-id="25d28-104">ClientSideXML</span><span class="sxs-lookup"><span data-stu-id="25d28-104">ClientSideXML</span></span>  
  
-   <span data-ttu-id="25d28-105">Basispfad</span><span class="sxs-lookup"><span data-stu-id="25d28-105">Base Path</span></span>  
  
-   <span data-ttu-id="25d28-106">Zuordnungsschema</span><span class="sxs-lookup"><span data-stu-id="25d28-106">Mapping Schema</span></span>  
  
 <span data-ttu-id="25d28-107">In dieser ADO-Beispielanwendung wird eine XML-Vorlage, die aus einer XPath-Abfrage (root) besteht, für das XSD-Zuordnungsschema (MySchema.xml) angegeben, das unter [Ausführen von XPath-Abfragen &#40;SQLXMLOLEDB-Anbieter&#41;](executing-xpath-queries-sqlxmloledb-provider.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="25d28-107">In this sample ADO application, an XML template that consists of an XPath query (root) is specified against the XSD mapping schema (MySchema.xml) that is described in [Executing XPath Queries &#40;SQLXMLOLEDB Provider&#41;](executing-xpath-queries-sqlxmloledb-provider.md).</span></span>  
  
 <span data-ttu-id="25d28-108">Die Mapping-Schema Eigenschaft stellt das XSD-Zuordnungsschema bereit, für das die XPath-Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="25d28-108">The Mapping Schema property provides the XSD mapping schema against which the XPath query is executed.</span></span> <span data-ttu-id="25d28-109">Die Eigenschaft Basispfad stellt den Dateipfad zum Zuordnungsschema bereit.</span><span class="sxs-lookup"><span data-stu-id="25d28-109">The Base Path property provides the file path to the mapping schema.</span></span>  
  
 <span data-ttu-id="25d28-110">Die ClientSideXML-Eigenschaft ist auf true festgelegt.</span><span class="sxs-lookup"><span data-stu-id="25d28-110">The ClientSideXML property is set to True.</span></span> <span data-ttu-id="25d28-111">Deshalb wird das XML-Dokument auf dem Client generiert.</span><span class="sxs-lookup"><span data-stu-id="25d28-111">Therefore, the XML document is generated on the client.</span></span>  
  
 <span data-ttu-id="25d28-112">In der Anwendung wird eine XPath-Abfrage direkt angegeben.</span><span class="sxs-lookup"><span data-stu-id="25d28-112">In the application, an XPath query is specified directly.</span></span> <span data-ttu-id="25d28-113">Daher muss der Dialekt {5d531cb2-e6ed-11d2-b252-00c04f681b71} eingeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="25d28-113">Therefore, the dialect {5d531cb2-e6ed-11d2-b252-00c04f681b71} must be included.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25d28-114">Im Code müssen Sie den Namen der Instanz von Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der Verbindungszeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="25d28-114">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="25d28-115">In diesem Beispiel wird überdies die Verwendung von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) als Datenanbieter beschrieben, was die Installation zusätzlicher Netzwerkclientsoftware erforderlich macht.</span><span class="sxs-lookup"><span data-stu-id="25d28-115">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="25d28-116">Weitere Informationen finden Sie unter [System Anforderungen für SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="25d28-116">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub Main()  
  
   Dim oTestStream As New ADODB.Stream  
   Dim oTestConnection As New ADODB.Connection  
   Dim oTestCommand As New ADODB.Command  
  
   oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security=SSPI;"  
  
   oTestCommand.ActiveConnection = oTestConnection  
   oTestCommand.Properties("ClientSideXML") = "False"  
  
   oTestCommand.CommandText = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'> " & _  
        " <sql:xpath-query mapping-schema='mySchema.xml' > " & _  
        "   root " & _  
        "   </sql:xpath-query> " & _  
        " </ROOT> "  
   oTestStream.Open  
   ' You need the dialect if you are executing a template.  
   oTestCommand.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
   oTestCommand.Properties("Output Stream").Value = oTestStream  
   oTestCommand.Properties("Base Path").Value = "c:\Schemas\SQLXML4\TemplateWithXPath\"  
   oTestCommand.Properties("Mapping Schema").Value = "mySchema.xml"  
   oTestCommand.Properties("Output Encoding") = "utf-8"  
   oTestCommand.Execute , , adExecuteStream  
   oTestStream.Position = 0  
   oTestStream.Charset = "utf-8"  
   Debug.Print oTestStream.ReadText(adReadAll)  
  
End Sub  
  
Sub Form_Load()  
   Main  
End Sub  
```  
  
 <span data-ttu-id="25d28-117">Das ist das Schema:</span><span class="sxs-lookup"><span data-stu-id="25d28-117">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
   xmlns:sql='urn:schemas-microsoft-com:mapping-schema'>  
 <xsd:element name= 'root' sql:is-constant='1'>   
    <xsd:complexType>  
       <xsd:sequence>  
         <xsd:element ref = 'Contact'/>  
       </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
  
  <xsd:element name='Contact' sql:relation='Person.Contact'>  
     <xsd:complexType>  
          <xsd:attribute name='ContactID' type='xsd:integer' />  
          <xsd:attribute name='FirstName' type='xsd:string'/>   
          <xsd:attribute name='LastName' type='xsd:string' />   
     </xsd:complexType>  
   </xsd:element>  
</xsd:schema>  
```  
  
  
