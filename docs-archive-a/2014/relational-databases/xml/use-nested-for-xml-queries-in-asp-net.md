---
title: Verwenden geschachtelter FOR XML-Abfragen in ASP.NET | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, nested FOR XML queries
- queries [XML in SQL Server], ASP.NET and
- nested FOR XML queries in ASP.NET
- ASP.NET [SQL Server]
ms.assetid: 691ac7dd-afc5-4760-932c-2b1dcd9394ed
author: rothja
ms.author: jroth
ms.openlocfilehash: 1218b4ad46f0d21d42ba480d68b29d7c39b03ea2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609752"
---
# <a name="use-nested-for-xml-queries-in-aspnet"></a><span data-ttu-id="07681-102">Verwenden geschachtelter FOR XML-Abfragen in ASP.NET</span><span class="sxs-lookup"><span data-stu-id="07681-102">Use Nested FOR XML Queries in ASP.NET</span></span>
  <span data-ttu-id="07681-103">In diesem Beispiel gibt eine ASP.NET-Anwendung XML-Code an einen Browser zurück, indem sie eine gespeicherte Prozedur in SQL Server ausführt.</span><span class="sxs-lookup"><span data-stu-id="07681-103">In this example, an ASP.NET application returns XML to a browser by executing a stored procedure in SQL Server.</span></span> <span data-ttu-id="07681-104">Die gespeicherte Prozedur generiert mithilfe von geschachtelten Abfragen XML.</span><span class="sxs-lookup"><span data-stu-id="07681-104">The stored procedure generates XML using nested queries.</span></span> <span data-ttu-id="07681-105">Eine ähnliche SELECT-Anweisung enthält das Thema [Geschachtelte FOR XML-Abfragen](generate-siblings-with-a-nested-auto-mode-query.md).</span><span class="sxs-lookup"><span data-stu-id="07681-105">A similar SELECT statement is shown in the topic [Generating Siblings by Using a Nested AUTO Mode Query](generate-siblings-with-a-nested-auto-mode-query.md).</span></span> <span data-ttu-id="07681-106">In diesem Beispiel wird eine Möglichkeit veranschaulicht, geschachtelte FOR XML-Abfragen zu verwenden, um elementzentriertes XML in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu generieren.</span><span class="sxs-lookup"><span data-stu-id="07681-106">This example demonstrates one way to use nested FOR XML queries to generate element-centric XML in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="07681-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07681-107">Example</span></span>  
  
```  
CREATE PROC GetSalesOrderInfo AS  
SELECT   
      (SELECT top 2 SalesOrderID, SalesPersonID, CustomerID,  
         (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
           from Sales.SalesOrderDetail  
            WHERE  SalesOrderDetail.SalesOrderID = SalesOrderHeader.SalesOrderID  
            FOR XML AUTO, TYPE)  
      FROM  Sales.SalesOrderHeader  
        WHERE SalesOrderHeader.SalesOrderID = SalesOrder.SalesOrderID  
      for xml auto, type),  
        (SELECT *   
         FROM  (SELECT SalesPersonID, EmployeeID  
              FROM Sales.SalesPerson, HumanResources.Employee  
              WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As SalesPerson  
         WHERE  SalesPerson.SalesPersonID = SalesOrder.SalesPersonID  
       FOR XML AUTO, TYPE, ELEMENTS)  
FROM (SELECT SalesOrderHeader.SalesOrderID, SalesOrderHeader.SalesPersonID  
      FROM Sales.SalesOrderHeader, Sales.SalesPerson  
      WHERE SalesOrderHeader.SalesPersonID = SalesPerson.SalesPersonID  
     ) as SalesOrder  
ORDER BY SalesOrder.SalesOrderID  
FOR XML AUTO, TYPE  
GO  
```  
  
 <span data-ttu-id="07681-108">Dies ist die ASPX-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="07681-108">This is the .aspx application.</span></span> <span data-ttu-id="07681-109">Sie führt die gespeicherte Prozedur aus und gibt den XML-Code im Browser zurück:</span><span class="sxs-lookup"><span data-stu-id="07681-109">It executes the stored procedure and returns XML in the browser:</span></span>  
  
```  
<%@LANGUAGE=C# Debug=true %>  
<%@import Namespace="System.Xml"%>  
<%@import namespace="System.Data.SqlClient" %><%  
Response.Expires = -1;  
Response.ContentType = "text/xml";  
%>  
  
<%  
using(System.Data.SqlClient.SqlConnection c = new System.Data.SqlClient.SqlConnection("Data Source=server;Database=AdventureWorks;Integrated Security=SSPI;"))  
using(System.Data.SqlClient.SqlCommand cmd = c.CreateCommand())  
{  
   cmd.CommandText = "GetSalesOrderInfo";  
   cmd.CommandType = CommandType.StoredProcedure;  
   cmd.Connection.Open();  
   System.Xml.XmlReader r = cmd.ExecuteXmlReader();  
   System.Xml.XmlTextWriter w = new System.Xml.XmlTextWriter(Response.Output);  
   w.WriteStartElement("Root");  
   r.MoveToContent();  
   while(! r.EOF)  
   {  
      w.WriteNode(r, true);  
   }  
   w.WriteEndElement();  
   w.Flush();  
}  
%>  
```  
  
##### <a name="to-test-the-application"></a><span data-ttu-id="07681-110">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="07681-110">To test the application</span></span>  
  
1.  <span data-ttu-id="07681-111">Erstellen Sie die gespeicherte Prozedur in der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="07681-111">Create the stored procedure in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="07681-112">Speichern Sie die ASPX-Anwendung in c:\inetpub\wwwroot-Verzeichnis (GetSalesOrderInfo.aspx).</span><span class="sxs-lookup"><span data-stu-id="07681-112">Save the .aspx application in the c:\inetpub\wwwroot directory (GetSalesOrderInfo.aspx).</span></span>  
  
3.  <span data-ttu-id="07681-113">Führen Sie die Anwendung aus ( http://server/GetSalesOrderInfo.aspx) .</span><span class="sxs-lookup"><span data-stu-id="07681-113">Execute the application (http://server/GetSalesOrderInfo.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07681-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07681-114">See Also</span></span>  
 [<span data-ttu-id="07681-115">Verwenden von geschachtelten FOR XML-Abfragen</span><span class="sxs-lookup"><span data-stu-id="07681-115">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
