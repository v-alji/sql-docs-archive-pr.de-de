---
title: Ausführen von SQL-Abfragen (SQLXMLOLEDB-Anbieter) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML], SQLXMLOLEDB Provider
- xml root property [SQLXML]
- SQLXMLOLEDB Provider, executing SQL queries
- SQL queries [SQLXML]
ms.assetid: 50334cf5-9c87-4c00-9beb-e08577c4fa82
author: rothja
ms.author: jroth
ms.openlocfilehash: a1e2cc87f90700e3b81a5a2ec3dd80f219a9b1d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619749"
---
# <a name="executing-sql-queries-sqlxmloledb-provider"></a><span data-ttu-id="3fc38-102">Ausführen von SQL-Abfragen (SQLXMLOLEDB-Anbieter)</span><span class="sxs-lookup"><span data-stu-id="3fc38-102">Executing SQL Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="3fc38-103">Dieses Beispiel veranschaulicht die Verwendung der folgenden SQLXMLOLEDB-anbieterspezifischen Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="3fc38-103">This example illustrates the use of the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   <span data-ttu-id="3fc38-104">ClientSideXML</span><span class="sxs-lookup"><span data-stu-id="3fc38-104">ClientSideXML</span></span>  
  
-   <span data-ttu-id="3fc38-105">XML-Stamm</span><span class="sxs-lookup"><span data-stu-id="3fc38-105">xml root</span></span>  
  
 <span data-ttu-id="3fc38-106">In dieser clientseitigen ADO-Beispielanwendung wird eine einfache SQL-Abfrage auf dem Client ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3fc38-106">In this client-side ADO sample application, a simple SQL query is executed on the client.</span></span> <span data-ttu-id="3fc38-107">Da die ClientSideXML-Eigenschaft auf true festgelegt ist, wird die SELECT-Anweisung ohne die for XML-Klausel an den Server gesendet.</span><span class="sxs-lookup"><span data-stu-id="3fc38-107">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="3fc38-108">Der Server führt die Abfrage aus und gibt ein Rowset an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="3fc38-108">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="3fc38-109">Der Client wendet dann die FOR XML-Transformation auf das Rowset an und generiert ein XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="3fc38-109">The client then applies the FOR XML transformation to the rowset and produces an XML document.</span></span>  
  
 <span data-ttu-id="3fc38-110">Die XML-Stamm Eigenschaft stellt das einzige Stamm Element der obersten Ebene für das generierte XML-Dokument bereit.</span><span class="sxs-lookup"><span data-stu-id="3fc38-110">The xml root property provides the single top-level root element for the XML document that is generated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3fc38-111">Im Code müssen Sie den Namen der Instanz von Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der Verbindungszeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3fc38-111">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="3fc38-112">In diesem Beispiel wird überdies die Verwendung von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) als Datenanbieter angegeben, was die Installation zusätzlicher Netzwerkclientsoftware erforderlich macht.</span><span class="sxs-lookup"><span data-stu-id="3fc38-112">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider, which requires additional network client software to be installed.</span></span> <span data-ttu-id="3fc38-113">Weitere Informationen finden Sie unter [System Anforderungen für SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="3fc38-113">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security=SSPI ;"  
oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
oTestCommand.CommandText = "SELECT TOP 10 FirstName, LastName FROM Person.Contact FOR XML AUTO"  
oTestStream.Open  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("xml root") = "root"  
oTestCommand.Execute , , adExecuteStream  
  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
  
