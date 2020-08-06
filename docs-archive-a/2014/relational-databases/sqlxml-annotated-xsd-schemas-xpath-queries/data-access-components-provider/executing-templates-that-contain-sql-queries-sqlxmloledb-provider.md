---
title: Ausführen von Vorlagen, die SQL-Abfragen enthalten (SQLXMLOLEDB-Anbieter) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- templates [SQLXML]
- SQLXMLOLEDB Provider, executing template files
- templates [SQLXML], SQL queries
- XML templates [SQLXML]
- SQL queries [SQLXML]
ms.assetid: ff2bc36f-e3fb-4d8f-8e3a-2680a39eda11
author: rothja
ms.author: jroth
ms.openlocfilehash: c3d3bc340612286e211d85f52a3d914d1d1b6b9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619035"
---
# <a name="executing-templates-that-contain-sql-queries-sqlxmloledb-provider"></a><span data-ttu-id="43c98-102">Ausführen von Vorlagen, die SQL-Abfragen enthalten (SQLXMLOLEDB-Anbieter)</span><span class="sxs-lookup"><span data-stu-id="43c98-102">Executing Templates That Contain SQL Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="43c98-103">Dieses Beispiel veranschaulicht die Verwendung der anbieterspezifischen SQLXMLOLEDB-Eigenschaft ClientSideXML.</span><span class="sxs-lookup"><span data-stu-id="43c98-103">This example illustrates the use of the SQLXMLOLEDB Provider-specific property ClientSideXML.</span></span> <span data-ttu-id="43c98-104">In dieser clientseitigen ADO-Beispielanwendung wird eine XML-Vorlage, die aus einer einfachen SQL-Abfrage besteht, auf dem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="43c98-104">In this client-side ADO sample application, an XML template that consists of an SQL query is executed on the server.</span></span>  
  
 <span data-ttu-id="43c98-105">Da die ClientSideXML-Eigenschaft auf true festgelegt ist, wird die SELECT-Anweisung ohne die for XML-Klausel an den Server gesendet.</span><span class="sxs-lookup"><span data-stu-id="43c98-105">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="43c98-106">Der Server führt die Abfrage aus und gibt ein Rowset an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="43c98-106">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="43c98-107">Der Client wendet dann die FOR XML-Transformation auf das Rowset an und generiert ein XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="43c98-107">The client then applies the FOR XML transformation to the rowset and produces an XML document.</span></span>  
  
 <span data-ttu-id="43c98-108">Die XML-Vorlage stellt ein einzelnes Stamm Element der obersten Ebene ( \<ROOT> ) für das generierte XML-Dokument bereit. Daher wird die XML-Stamm Eigenschaft nicht bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="43c98-108">The XML template provides a single top-level root element (\<ROOT>) for the XML document that is generated; therefore, the xml root property is not provided.</span></span>  
  
 <span data-ttu-id="43c98-109">Zum Ausführen der XML-Vorlagen muss der Dialekt {5d531cb2-e6ed-11d2-b252-00c04f681b71} angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="43c98-109">To execute XML templates, the dialect {5d531cb2-e6ed-11d2-b252-00c04f681b71} must be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43c98-110">Im Code müssen Sie den Namen der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der Verbindungszeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="43c98-110">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="43c98-111">In diesem Beispiel wird überdies die Verwendung von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) als Datenanbieter beschrieben, was die Installation zusätzlicher Netzwerkclientsoftware erforderlich macht.</span><span class="sxs-lookup"><span data-stu-id="43c98-111">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="43c98-112">Weitere Informationen finden Sie unter [System Anforderungen für SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="43c98-112">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
  
Sub Main()  
  Dim oTestStream As New ADODB.Stream  
  Dim oTestConnection As New ADODB.Connection  
  Dim oTestCommand As New ADODB.Command  
  oTestConnection.Open "Provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Data Source=SqlServerName;Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
  
  Set oTestCommand.ActiveConnection = oTestConnection  
  oTestCommand.Properties("ClientSideXML") = True  
  oTestCommand.CommandText = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'> " & _  
        " <sql:query> " & _  
        "   SELECT TOP 10 FirstName, LastName FROM Person.Contact FOR XML AUTO " & _  
        "   </sql:query> " & _  
        " </ROOT> "  
  oTestStream.Open  
  ' You need the dialect if you are executing   
  ' XML templates (not for SQL queries).  
  oTestCommand.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  oTestCommand.Properties("Output Stream").Value = oTestStream  
  oTestCommand.Execute , , adExecuteStream  
  
  oTestStream.Position = 0  
  oTestStream.Charset = "utf-8"  
  Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
  
Sub Form_Load()  
  Main  
End Sub  
```  
  
  
