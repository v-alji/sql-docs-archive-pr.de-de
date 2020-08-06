---
title: Verhindern von ungültigen Anforderungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- invalid requests [Reporting Services]
- exceptions [Reporting Services], invalid requests
- valid requests [Reporting Services]
ms.assetid: 4a4a2d97-4c10-43a9-8298-ef5a820ea549
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 12343955c46fb98fea75048a38749b1db993fa11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621342"
---
# <a name="preventing-invalid-requests"></a><span data-ttu-id="a0047-102">Verhindern von ungültigen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0047-102">Preventing Invalid Requests</span></span>
  <span data-ttu-id="a0047-103">Sie können verhindern, dass bestimmte Ausnahmearten ausgelöst werden, indem Sie den Anwendungsablauf analysieren und sicherstellen, dass die an den Berichtsserver gesendeten Anforderungen gültig sind.</span><span class="sxs-lookup"><span data-stu-id="a0047-103">You can prevent some types of exceptions from being thrown by analyzing your application flow and ensuring that the requests being sent to the report server are valid.</span></span> <span data-ttu-id="a0047-104">In Anwendungen, in denen die Benutzer den Namen eines Berichts, einer Datenquelle oder eines anderen Berichtsserverelements ändern oder aktualisieren dürfen, sollten Sie beispielsweise den Text, den ein Benutzer eingeben kann, validieren.</span><span class="sxs-lookup"><span data-stu-id="a0047-104">For example, in applications that enable users to add or update the name of a report, data source, or other report server item, you should validate the text that a user might enter.</span></span> <span data-ttu-id="a0047-105">Sie sollten stets nach reservierten Zeichen suchen, bevor die Anforderung an einen Berichtsserver gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a0047-105">You should always check for reserved characters before sending the request to a report server.</span></span> <span data-ttu-id="a0047-106">Verwenden Sie bedingte **if**-Anweisungen oder andere logische Konstrukte im Code, um den Benutzer darauf aufmerksam zu machen, dass die erforderlichen Bedingungen für das Senden der Anforderung an den Berichtsserver nicht erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="a0047-106">Use conditional **if** statements or other logical constructs in your code to alert the user that they have not met the conditions necessary to send requests to the report server.</span></span>  
  
 <span data-ttu-id="a0047-107">Im folgenden vereinfachten C#-Beispiel erhalten die Benutzer eine freundliche Fehlermeldung, wenn Sie versuchen, einen Bericht mit einem Namen zu erstellen, der einen Schrägstrich (/) enthält.</span><span class="sxs-lookup"><span data-stu-id="a0047-107">In the following, simplified C# example, users are presented with a friendly error message when they attempt to create a report with a name that contains a forward slash (/) character.</span></span>  
  
```  
// C#  
private void PublishReport()  
{  
   int index;  
   string reservedChar;  
   string message;  
  
   // Check the text value of the name text box for "/",  
   // a reserved character  
   index = nameTextBox.Text.IndexOf(@"/");  
  
   if ( index != -1) // The text contains the character  
   {  
      reservedChar = nameTextBox.Text.Substring(index, 1);  
      // Build a user-friendly error message  
      message = "The name of the report cannot contain the reserved character " +  
         "\"" + reservedChar + "\". " +  
         "Please enter a valid name for the report. " +  
         "For more information about reserved characters, " +  
         "see the help documentation";  
  
      MessageBox.Show(message, "Invalid Input Error");  
   }  
   else // Publish the report  
   {  
      Byte[] definition = null;  
      Warning[] warnings = {};  
      string name = nameTextBox.Text;  
  
      FileStream stream = File.OpenRead("MyReport.rdl");  
      definition = new Byte[stream.Length];  
      stream.Read(definition, 0, (int) stream.Length);  
      stream.Close();  
      // Create report with user-defined name  
      rs.CreateCatalogItem("Report", name, "/Samples", false, definition, null, out warnings);  
      MessageBox.Show("Report: {0} created successfully", name);  
   }  
}  
```  
  
 <span data-ttu-id="a0047-108">Weitere Informationen zu den verschiedenen Fehlerarten, die verhindert werden können, bevor Anforderungen an den Berichtsserver gesendet werden, finden Sie unter [Tabelle für SoapException-Fehler](../soapexception-class/soapexception-errors-table.md).</span><span class="sxs-lookup"><span data-stu-id="a0047-108">For more information about the types of errors that can be prevented before requests are sent to the report server, see [SoapException Errors Table](../soapexception-class/soapexception-errors-table.md).</span></span> <span data-ttu-id="a0047-109">Weitere Informationen zur Vertiefung des vorherigen Beispiels mithilfe von try/catch-Blöcken finden Sie unter [Verwenden von Try- und Catch-Blöcken](using-try-and-catch-blocks.md).</span><span class="sxs-lookup"><span data-stu-id="a0047-109">For more information about further enhancing the previous example using try/catch blocks, see [Using Try and Catch Blocks](using-try-and-catch-blocks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0047-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0047-110">See Also</span></span>  
 <span data-ttu-id="a0047-111">[Einführung in die Ausnahmebehandlung in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="a0047-111">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="a0047-112">Reporting Services-SoapException-Klasse</span><span class="sxs-lookup"><span data-stu-id="a0047-112">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
