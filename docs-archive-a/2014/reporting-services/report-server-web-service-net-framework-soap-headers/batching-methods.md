---
title: Methoden der Batchverarbeitung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- methods [Reporting Services], batches
- BatchHeader SOAP header
- Web service [Reporting Services], methods
- Report Server Web service, batching
- batches [Reporting Services]
- XML Web service [Reporting Services], methods
- locking [Reporting Services]
- multiple Web service methods
ms.assetid: 86435534-c9fe-4b49-b88c-7fb6d21976b0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c778da186fdbbfaed17b9635d9ca7309a369552b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621337"
---
# <a name="batching-methods"></a><span data-ttu-id="09a2a-102">Methoden der Batchverarbeitung</span><span class="sxs-lookup"><span data-stu-id="09a2a-102">Batching Methods</span></span>
  <span data-ttu-id="09a2a-103">Durch die Verwendung von SOAP-Headern in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] können Sie mehrere Webdienstmethoden in einen einzelnen Vorgang aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="09a2a-103">The use of SOAP headers in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] enables you to include multiple Web service methods in a single operation.</span></span> <span data-ttu-id="09a2a-104">Die Methoden werden im Rahmen einer Datenbanktransaktion in der Reihenfolge ihres Aufrufs ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="09a2a-104">Methods run within the scope of a single database transaction, in the order in which they are called.</span></span>  
  
 <span data-ttu-id="09a2a-105">Rollback hat den Vorteil, dass aus mehreren Methoden bestehende Batchvorgänge verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="09a2a-105">Rollback is one advantage of using multiple-method batch operations.</span></span> <span data-ttu-id="09a2a-106">Wenn ein Fehler in einem der Methodenaufrufe auftritt, während ein Batch ausgeführt wird, stoppt der Berichtsserver die Verarbeitung und führt ein Rollback aller vorherigen Vorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="09a2a-106">If an error occurs on any of the method calls while a batch is running, the report server stops running the batch and rolls back any previous operations.</span></span> <span data-ttu-id="09a2a-107">Dies ist dann sinnvoll, wenn ein Methodenaufruf von der erfolgreichen Durchführung anderer Methodenaufrufe im Batch abhängt.</span><span class="sxs-lookup"><span data-stu-id="09a2a-107">This is useful when a method call depends on the successful completion of other method calls in that batch.</span></span>  
  
 <span data-ttu-id="09a2a-108">Der Webdienst enthält keine Sperrsemantik für aus mehreren Methoden bestehende Batchvorgänge.</span><span class="sxs-lookup"><span data-stu-id="09a2a-108">The Web service does not provide locking semantics for multiple-method batch operations.</span></span> <span data-ttu-id="09a2a-109">Zeilen in einer Berichtsserver-Datenbank werden erst dann für das Update gesperrt, wenn die Meldung an den Server gesendet wird und der Execute-Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="09a2a-109">Rows in the report server database are not locked for updating until the message is sent to the server and the Execute command is called.</span></span>  
  
 <span data-ttu-id="09a2a-110">Es ist keine Parallelitätssteuerung vorhanden, die sicherstellt, dass die Datenbank nicht geändert wurde, seit die Daten zum letzten Mal gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="09a2a-110">There are also no concurrency controls to guarantee that the database has not changed since the data was last read.</span></span> <span data-ttu-id="09a2a-111">Wenn zwei Clients dasselbe Element ändern, ist das letzte Update erfolgreich, wenn die Parameter noch gültig sind (z. B. wenn das Element nicht umbenannt wurde).</span><span class="sxs-lookup"><span data-stu-id="09a2a-111">If two clients modify the same item, the last update succeeds if the parameters are still valid (for example, the item has not been renamed).</span></span>  
  
 <span data-ttu-id="09a2a-112">Im folgenden Beispiel wird die <xref:ReportService2005.ReportingService2005.CreateFolder%2A>-Methode dreimal aufgerufen, und diese Aufrufe werden in einem Batch ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="09a2a-112">The following example calls the <xref:ReportService2005.ReportingService2005.CreateFolder%2A> method three times and runs these calls as a single batch.</span></span> <span data-ttu-id="09a2a-113">Wenn einer der Aufrufe von <xref:ReportService2005.ReportingService2005.CreateFolder%2A> fehlschlägt, wird der gesamte Batch abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="09a2a-113">If any of the calls to <xref:ReportService2005.ReportingService2005.CreateFolder%2A> fail, the entire batch is canceled.</span></span>  
  
```vb  
Imports System  
Imports System.Web.Services.Protocols  
Imports myNamespace.MyReferenceName  
  
Class Sample  
    Sub Main(args() As String)  
        Dim rs As New ReportingService2005()  
        rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
      ' Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/ReportService2005.asmx"  
  
        Dim bh As New BatchHeader()  
  
        bh.BatchId = service.CreateBatch()  
        rs.BatchHeaderValue = bh  
        rs.CreateFolder("New Folder1", "/", Nothing)  
        rs.CreateFolder("New Folder2", "/", Nothing)  
        rs.CreateFolder("New Folder3", "/", Nothing)  
  
        Console.WriteLine("Creating folders...")  
        rs.BatchHeaderValue = bh  
        rs.ExecuteBatch()  
        Console.WriteLine("Folders created successfully.")  
  
        rs.BatchHeaderValue = Nothing  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Web.Services.Protocols;   
using myNamespace.MyReferenceName;  
  
class Sample  
{  
    static void Main(string[] args)  
    {  
        ReportingService2005 rs = new ReportingService2005();  
        rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
      // Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/ReportService2005.asmx"  
  
        BatchHeader bh = new BatchHeader();  
  
        bh1.BatchID = service.CreateBatch();  
        rs.BatchHeaderValue = bh;  
        rs.CreateFolder("New Folder1", "/", null);  
        rs.CreateFolder("New Folder2", "/", null);  
        rs.CreateFolder("New Folder3", "/", null);  
  
        Console.WriteLine("Creating folders...");  
        rs.BatchHeaderValue = bh1;  
        rs.ExecuteBatch();  
        Console.WriteLine("Folders created successfully.");  
  
        rs.BatchHeaderValue = null;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="09a2a-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="09a2a-114">See Also</span></span>  
 <xref:ReportService2005.ReportingService2005.CancelBatch%2A>   
 <xref:ReportService2005.ReportingService2005.CreateBatch%2A>   
 <span data-ttu-id="09a2a-115">[Technische Referenz &#40;SSRS&#41;](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="09a2a-115">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="09a2a-116">Verwenden von Reporting Services SOAP-Headern</span><span class="sxs-lookup"><span data-stu-id="09a2a-116">Using Reporting Services SOAP Headers</span></span>](using-reporting-services-soap-headers.md)  
  
  
