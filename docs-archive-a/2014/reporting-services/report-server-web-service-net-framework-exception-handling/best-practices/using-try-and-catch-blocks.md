---
title: Verwenden von „Try und Catch“-Blöcken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], try/catch blocks
- try/catch blocks [Reporting Services]
ms.assetid: a7a9ef53-e3b6-4bf7-81f3-d85615954e6f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a6aadb392fa4117484f3373ae232c3ed9c4b1d63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723373"
---
# <a name="using-try-and-catch-blocks"></a><span data-ttu-id="eb84d-102">Verwenden von „Try und Catch“-Blöcken</span><span class="sxs-lookup"><span data-stu-id="eb84d-102">Using Try and Catch Blocks</span></span>
  <span data-ttu-id="eb84d-103">Nachdem Sie ungültige Anforderungen an den Berichtsserver eingeschränkt haben, indem Sie bedingte Anweisungen zum Code hinzugefügt haben, sollten Sie mithilfe von try/catch-Blöcken eine adäquate Ausnahmebehandlung festlegen.</span><span class="sxs-lookup"><span data-stu-id="eb84d-103">After you limit invalid requests to the report server by adding conditional statements to your code, you should supply adequate exception handling through the use of try/catch blocks.</span></span> <span data-ttu-id="eb84d-104">Diese Technik stellt eine weitere Stufe des Schutzes gegen ungültige Anforderungen dar.</span><span class="sxs-lookup"><span data-stu-id="eb84d-104">This technique provides another layer of protection against requests that are not valid.</span></span> <span data-ttu-id="eb84d-105">Wenn eine Anforderung an den Berichtsserver in einem try-Block enthalten ist und diese Anforderung dazu führt, dass der Berichtsserver eine Ausnahme auslöst, wird die Ausnahme im catch-Block erfasst. Damit wird ein unerwarteter Abbruch Ihrer Anwendung verhindert.</span><span class="sxs-lookup"><span data-stu-id="eb84d-105">If a request to the report server is encased in a try block and that request causes the report server to throw an exception, the exception is caught in the catch block, thus preventing your application from ending unexpectedly.</span></span> <span data-ttu-id="eb84d-106">Sobald die Ausnahme erfasst ist, können Sie den Benutzer mit der Ausnahme anweisen, einen anderen Vorgang auszuführen, oder Sie teilen ihm einfach auf freundliche Weise mit, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="eb84d-106">Once the exception is caught, you can use the exception to either instruct the user to do something differently, or just let the user know, in a friendly way, that an error has occurred.</span></span> <span data-ttu-id="eb84d-107">Sie können dann einen finally-Block verwenden, um einen Cleanup vorhandener Ressourcen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="eb84d-107">You can then use a finally block to clean up any resources.</span></span> <span data-ttu-id="eb84d-108">Idealerweise sollten Sie einen Plan für die allgemeine Ausnahmebehandlung generieren, um eine unnötige Verdoppelung von try/catch-Blöcken zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="eb84d-108">Ideally, you should generate a general exception-handling plan to avoid unnecessary duplication of try/catch blocks.</span></span>  
  
 <span data-ttu-id="eb84d-109">Im folgenden Beispiel werden try/catch-Blöcke verwendet, um die Zuverlässigkeit des Ausnahmebehandlungscodes zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="eb84d-109">The following example uses try/catch blocks to enhance the reliability of the exception handling code.</span></span>  
  
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
         "consult the online documentation";  
  
      MessageBox.Show(message, "Invalid Input Error");  
   }  
   else // Publish the report  
   {  
      Byte[] definition = null;  
      Warning[] warnings = {};  
      string name = nameTextBox.Text;  
  
      try  
      {  
         FileStream stream = File.OpenRead("MyReport.rdl");  
         definition = new Byte[stream.Length];  
         stream.Read(definition, 0, (int) stream.Length);  
         stream.Close();  
         // Create report with user-defined name  
         rs.CreateCatalogItem("Report", name, "/Samples", false, definition, null, out warnings);  
         MessageBox.Show("Report: {0} created successfully", name);  
      }  
  
      // Catch expected exceptions beginning with the most specific,  
      // moving to the least specific  
      catch(IOException ex)  
      {  
         MessageBox.Show(ex.Message, "File IO Exception");  
      }  
  
      catch (SoapException ex)  
      {  
         // The exception is a SOAP exception, so use  
         // the Detail property's Message element.  
         MessageBox.Show(ex.Detail["Message"].InnerXml, "SOAP Exception");   
      }  
  
      catch (Exception ex)  
      {  
         MessageBox.Show(ex.Message, "General Exception");  
      }  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="eb84d-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb84d-110">See Also</span></span>  
 <span data-ttu-id="eb84d-111">[Einführung in die Ausnahmebehandlung in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="eb84d-111">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="eb84d-112">Reporting Services-SoapException-Klasse</span><span class="sxs-lookup"><span data-stu-id="eb84d-112">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
