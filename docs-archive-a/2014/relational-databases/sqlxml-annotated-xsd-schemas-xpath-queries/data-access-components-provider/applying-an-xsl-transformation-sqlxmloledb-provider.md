---
title: Anwenden einer XSL-Transformation (SQLXMLOLEDB-Anbieter) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, applying XSL transformations
- applying XSL transformations [SQLXML]
- xsl property
- Base Path property
- XSL Transformations [SQLXML]
ms.assetid: cb5e41ab-dd20-4873-af20-f417bd1bbf6d
author: rothja
ms.author: jroth
ms.openlocfilehash: 7fbb427a95d9f2308bf65724758a4a1563b42575
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619036"
---
# <a name="applying-an-xsl-transformation-sqlxmloledb-provider"></a><span data-ttu-id="4e7ce-102">Anwenden einer XSL-Transformation (SQLXMLOLEDB-Anbieter)</span><span class="sxs-lookup"><span data-stu-id="4e7ce-102">Applying an XSL Transformation (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="4e7ce-103">In dieser ADO-Beispielanwendung wird eine SQL-Abfrage ausgeführt und auf das Ergebnis eine XSL-Transformation angewendet.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-103">In this sample ADO application, an SQL query is executed, and an XSL transformation is applied to the result.</span></span> <span data-ttu-id="4e7ce-104">Wenn die ClientSideXML-Eigenschaft auf true festgelegt wird, wird die Verarbeitung des Rowsets auf der Clientseite erzwungen.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-104">Setting the ClientSideXML property to True enforces the processing of the rowset on the client side.</span></span> <span data-ttu-id="4e7ce-105">Der Befehlsdialekt wird auf {5d531cb2-e6ed-11d2-b252-00c04f681b71} festgelegt, da die SQL-Abfrage in einer Vorlage angegeben ist und dieser Dialekt angegeben werden muss, wenn eine Vorlage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-105">The command dialect is set to {5d531cb2-e6ed-11d2-b252-00c04f681b71}, because the SQL query is specified in a template and this dialect must be specified when executing a template.</span></span> <span data-ttu-id="4e7ce-106">Die XSL-Eigenschaft gibt die XSL-Datei an, die zum Anwenden der Transformation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-106">The xsl property specifies the XSL file to use to apply the transformation.</span></span> <span data-ttu-id="4e7ce-107">Der Wert der Basis Pfadeigenschaft wird verwendet, um nach der XSL-Datei zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-107">The value of Base Path property is used to search for the XSL file.</span></span> <span data-ttu-id="4e7ce-108">Wenn Sie einen Pfad im Wert der XSL-Eigenschaft angeben, ist der Pfad relativ zu dem Pfad, der in der Basis Pfadeigenschaft angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-108">If you specify a path in the value of the xsl property, the path is relative to the path that is specified in the Base Path property.</span></span>  
  
 <span data-ttu-id="4e7ce-109">In diesem Beispiel wird gezeigt, wie die folgenden für den SQLXMLOLEDB-Anbieter spezifischen Eigenschaften verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="4e7ce-109">This example shows how to use the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   <span data-ttu-id="4e7ce-110">ClientSideXML</span><span class="sxs-lookup"><span data-stu-id="4e7ce-110">ClientSideXML</span></span>  
  
-   <span data-ttu-id="4e7ce-111">XSL</span><span class="sxs-lookup"><span data-stu-id="4e7ce-111">xsl</span></span>  
  
 <span data-ttu-id="4e7ce-112">In dieser clientseitigen ADO-Beispielanwendung wird eine XML-Vorlage, die aus einer einfachen SQL-Abfrage besteht, auf dem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-112">In this client-side ADO sample application, an XML template that consists of an SQL query is executed on the server.</span></span>  
  
 <span data-ttu-id="4e7ce-113">Da die ClientSideXML-Eigenschaft auf true festgelegt ist, wird die SELECT-Anweisung ohne die for XML-Klausel an den Server gesendet.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-113">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="4e7ce-114">Der Server führt die Abfrage aus und gibt ein Rowset an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-114">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="4e7ce-115">Der Client wendet anschließend die FOR XML-Transformation auf das Rowset an und generiert das XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-115">The client then applies the FOR XML transformation to the rowset and produces the XML document.</span></span>  
  
 <span data-ttu-id="4e7ce-116">Die XSL-Eigenschaft wird in der Anwendung angegeben. Daher wird die XSL-Transformation auf das XML-Dokument angewendet, das auf dem Client generiert wird, und das Ergebnis ist eine Tabelle mit zwei Spalten.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-116">The xsl property is specified in the application; therefore, the XSL transformation is applied to the XML document that is generated on the client, and the result is a two-column table.</span></span>  
  
 <span data-ttu-id="4e7ce-117">Um den Vorlagen Befehl auszuführen, muss der XML-Vorlagen Dialekt "Dialekt-{5d531cb2-e6ed-11d2-b252-00c04f681b71}" angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-117">To execute the template command, the XML template dialect - {5d531cb2-e6ed-11d2-b252-00c04f681b71} - must be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e7ce-118">Im Code müssen Sie den Namen der Instanz von Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der Verbindungszeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-118">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="4e7ce-119">In diesem Beispiel wird überdies die Verwendung von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client als Datenanbieter angegeben, was die Installation zusätzlicher Netzwerkclientsoftware erforderlich macht.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-119">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="4e7ce-120">Weitere Informationen finden Sie unter [System Anforderungen für SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="4e7ce-120">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security=SSPI;"  
Set oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
oTestCommand.CommandText = _  
        "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql' >" & _  
       " <sql:query> " & _  
        "   SELECT TOP 25 FirstName, LastName FROM Person.Contact FOR XML AUTO " & _  
        "   </sql:query> " & _  
        " </ROOT> "  
oTestStream.Open  
' You need the dialect if you are executing a template.  
oTestCommand.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("Base Path").Value = "c:\Schemas\SQLXML4\ExecuteTemplateWithXSL\"  
oTestCommand.Properties("xsl").Value = "myxsl.xsl"  
oTestCommand.Execute , , adExecuteStream  
  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
 <span data-ttu-id="4e7ce-121">Im Folgenden finden Sie die XSL-Vorlage.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-121">The XSL template follows.</span></span> <span data-ttu-id="4e7ce-122">Aus der Anwendung dieser XSL-Vorlage ergibt sich eine zweispaltige Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-122">The result of applying this XSL template is a two-column table.</span></span>  
  
```  
<?xml version='1.0' encoding='UTF-8'?>            
 <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">   
  
    <xsl:template match = 'Person.Contact'>  
       <TR>  
         <TD><xsl:value-of select = '@FirstName' /></TD>  
         <TD><B><xsl:value-of select = '@LastName' /></B></TD>  
       </TR>  
    </xsl:template>  
    <xsl:template match = '/'>  
      <HTML>  
        <HEAD>  
           <STYLE>th { background-color: #CCCCCC }</STYLE>  
        </HEAD>  
        <BODY>  
         <TABLE border='1' style='width:300;'>  
           <TR><TH colspan='2'>Contacts</TH></TR>  
           <TR>  
              <TH >First name</TH>  
              <TH>Last name</TH>  
           </TR>  
           <xsl:apply-templates select = 'ROOT' />  
         </TABLE>  
        </BODY>  
      </HTML>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
  
